### Single responsibility

A [[Class]] should only have a single responsibility, a class that is focused on manipulating a list should be doing the [[DataBase]] connection nor the repository responsabilities, as it can be passed to other classes

###### wrong approach:

all the code stuffed together for no reason

```java
import java.sql.*;
import java.util.ArrayList;
import java.util.List;

public class UserManager {
    private Connection connection;
    private List<String> users = new ArrayList<>();

    public UserManager() {
        try {
            connection = DriverManager.getConnection("jdbc:mysql://localhost:3306/mydb", "user", "password");
        } catch (Exception e) {
            e.printStackTrace();
        }
    }

    public void fetchUsers() {
        try (Statement stmt = connection.createStatement();
             ResultSet rs = stmt.executeQuery("SELECT username FROM users")) {
            while (rs.next()) {
                users.add(rs.getString("username"));
            }
        } catch (Exception e) {
            e.printStackTrace();
        }
    }

    public void addUser(String user) {
        users.add(user);
    }

    public List<String> getUsers() {
        return users;
    }
}
```

###### correct approach

all the code correctly divided into modules

```java
import java.sql.*;

public class DBConnection {
    public static Connection getConnection() {
        try {
            return DriverManager.getConnection("jdbc:mysql://localhost:3306/mydb", "user", "password");
        } catch (Exception e) {
            e.printStackTrace();
            return null;
        }
    }
}
```

```java
import java.sql.*;
import java.util.ArrayList;
import java.util.List;

public class UserRepository {
    private Connection connection = DBConnection.getConnection();

    public List<String> fetchUsers() {
        List<String> users = new ArrayList<>();
        try (Statement stmt = connection.createStatement();
             ResultSet rs = stmt.executeQuery("SELECT username FROM users")) {
            while (rs.next()) {
                users.add(rs.getString("username"));
            }
        } catch (Exception e) {
            e.printStackTrace();
        }
        return users;
    }
}
```

```java
import java.util.ArrayList;
import java.util.List;

public class UserManager {
    private List<String> users = new ArrayList<>();

    public void loadUsers(UserRepository repository) {
        users = repository.fetchUsers();
    }

    public void addUser(String user) {
        users.add(user);
    }

    public List<String> getUsers() {
        return users;
    }
}

```

### Open/Close

[[Class]]es are open for extension but closed for modification

###### wrong approach:

the [[Class]] FolhaDePagamento will have to be changed if a new role is created, like a manager PJ

```java
class ContratoClt {
    public double salario() {
        // Implementação do cálculo do salário
        return 0.0;
    }
}

class Estagio {
    public double bolsaAuxilio() {
        // Implementação do cálculo da bolsa auxílio
        return 0.0;
    }
}

class FolhaDePagamento {
    private double saldo;

    public void calcular(Object funcionario) {
        if (funcionario instanceof ContratoClt) {
            this.saldo = ((ContratoClt) funcionario).salario();
        } else if (funcionario instanceof Estagio) {
            this.saldo = ((Estagio) funcionario).bolsaAuxilio();
        }
    }
}
```

###### correct approach:

all classes implements Remuneravel and overrides the [[Method]], now classes can be created without changing FolhaDePagamento

```java
interface Remuneravel {
    double remuneracao();
}

class ContratoClt implements Remuneravel {
    @Override
    public double remuneracao() {
        // Implementação do cálculo do salário
        return 0.0;
    }
}

class Estagio implements Remuneravel {
    @Override
    public double remuneracao() {
        // Implementação do cálculo da bolsa auxílio
        return 0.0;
    }
}

class ContratoPj implements Remuneravel {
    @Override
    public double remuneracao() {
        // Implementação do pagamento PJ
        return 0.0;
    }
}

class FolhaDePagamento {
    private double saldo;

    public void calcular(Remuneravel funcionario) {
        this.saldo = funcionario.remuneracao();
    }
}
```
### Liskov substitution

A subclass needs to be substituted by your superclass without altering the programs expected behavior, if we create an Ave class with a [[Method]] fly(), a subclass Penguim shouldnt be forced to implement it, because that would violate liskov substitution principle

###### wrong approach:

here the poor penguins are forced to implement voar(), even though the cant

```java
class Ave {
    String nome;

    public Ave(String nome) {
        this.nome = nome;
    }

    public void voar() {
        System.out.println(nome + " está voando.");
    }

    public void emitirSom() {
        System.out.println(nome + " está emitindo som.");
    }
}

class Andorinha extends Ave {
    public Andorinha(String nome) {
        super(nome);
    }
}

class Pinguim extends Ave {
    public Pinguim(String nome) {
        super(nome);
    }

    @Override
    public void voar() {
        throw new UnsupportedOperationException("Pinguins não podem voar!");
    }

    public void nadar() {
        System.out.println(nome + " está nadando.");
    }
}
```
###### correct approach:

Here with have a class Ave without actually a [[Method]] voar, but we create an [[Interface (Poo)]] AvesQueVoam that can be implemented when needed

```java
abstract class Ave {
    String nome;

    public Ave(String nome) {
        this.nome = nome;
    }

    public void emitirSom() {
        System.out.println(nome + " está emitindo som.");
    }
}

interface AvesQueVoam {
    void voar();
}

class Andorinha extends Ave implements AvesQueVoam {
    public Andorinha(String nome) {
        super(nome);
    }

    @Override
    public void voar() {
        System.out.println(nome + " está voando.");
    }
}

class Pinguim extends Ave {
    public Pinguim(String nome) {
        super(nome);
    }

    public void nadar() {
        System.out.println(nome + " está nadando.");
    }
}
```




### Interface segregation

Not forcing [[Class]]es to implement behaviors from an [[Interface (Poo)]] they dont need
###### wrong approach:

here an [[Interface (Poo)]] calculated both the area and the volume when some classes might not use it all

```java
interface IShapeAreaCalculator(){
  double calculateArea();
  double calculateVolume();
}

class Square implements IShapeAreaCalculator{
  double calculateArea(){ // calculate the area }
  double calculateVolume(){ // dummy implementation }
}

```
###### correct approach:

here the interface is correctly broken down into two interfaces, now not creating dumb implementations

```java
interface IAreaCalculator {
    double calculateArea();
}

interface IVolumeCalculator {
    double calculateVolume();
}

class Square implements IAreaCalculator {
    @Override
    public double calculateArea() { // calculate the area }
}

class Cube implements IAreaCalculator, IVolumeCalculator {
    @Override
    public double calculateArea() { // calculate the area }

    @Override
    public double calculateVolume() {// calculate the volume }
}
```

### Dependency inversion

High levels modules shouldnt depende on low level [[Module|Modules]], instead it should be the opposite of this, or, a dependency inversion

###### wrong approach:

NotificationService depends on EmailNotificationProvider and SMSNotificationProvider because the implementations are made in the low level modules, which dumb and should be done in the high level module

```java
// Step 1: Concrete implementations without an abstraction
class EmailNotificationProvider {
    public void sendEmail(String message) {
        System.out.println("Sending email: " + message);
    }
}

class SMSNotificationProvider {
    public void sendSMS(String message) {
        System.out.println("Sending SMS: " + message);
    }
}

// Step 2: High-level module depends on concrete implementations
class NotificationService {
    private final EmailNotificationProvider emailProvider;
    private final SMSNotificationProvider smsProvider;

    public NotificationService() {
        this.emailProvider = new EmailNotificationProvider();
        this.smsProvider = new SMSNotificationProvider();
    }

    public void notifyViaEmail(String message) {
        emailProvider.sendEmail(message);
    }

    public void notifyViaSMS(String message) {
        smsProvider.sendSMS(message);
    }
}
```
###### correct approach:

now the implementation is inside the NotificationService and the classes are being received as a parameter instead of creating instances and the implementation is being done in the high level module

```java
// Step 1: Define the abstraction (interface)
interface NotificationProvider {
    void send(String message);
}

// Step 2: Implement concrete providers
class EmailNotificationProvider implements NotificationProvider {
    @Override
    public void send(String message) {
        System.out.println("Sending email: " + message);
    }
}

class SMSNotificationProvider implements NotificationProvider {
    @Override
    public void send(String message) {
        System.out.println("Sending SMS: " + message);
    }
}

// Step 3: High-level module depends on the abstraction
class NotificationService {
    private final NotificationProvider provider;

    // Dependency injected via constructor
    public NotificationService(NotificationProvider provider) {
        this.provider = provider;
    }

    public void notifyUser(String message) {
        provider.send(message);
    }
}
```

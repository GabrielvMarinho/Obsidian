A guide for [[Java]] Integration with a database

Firstly we have to create a bridge from java to [[Sql]] so that they can communicate, for that, we use [[Drivers]]

Install [[MySql]] Connector J in [[Oracle]]

Open your projects > Project Structure > Libraries > Java > add your jar connector file

### Java code in the DB Class:

```
//las part checks if it exists and creates if not
private final String URL = "jdbc:mysql://localhost:3306/db_sistema_bancario?"+"createDatabaseIfNotExist=true";

private final String USER = "root";  
private final String PASSWORD = "";

public Connection getConnection() throws SQLException {  
    //class - statis method to connect to database 
    return DriverManager.getConnection(URL, USER, PASSWORD);  
}
```

### To execute the code:

```
Connection con = banco.getConnection();  
PreparedStatement ps = con.prepareStatement(  
        //stopping sql injections from happening 
        "INSERT INTO tb_conta " +  
                "(numero, titular, saldo, limite)" +  
                "VALUES(?, ?, ?, ?)");  
ps.setInt(1, conta.getNumero());  
ps.setString(2, conta.getTitular());  
ps.setDouble(3, conta.getSaldo());  
ps.setDouble(4, conta.getLimite());  
  
ps.execute();

//always close the connection because someone else has got to get their turn
con.close();
//u can use AutoCloseable in the try catch to make it easier
```

### Types of EXECUTE

execute: return true or false
executeUpdate: return how many rows were manipulated (Int)
executeLargeUpdate: return how many rows were manipulated (Long)
executeQuery: return a db query like a select


Check [[JavaCrudExample]] for a [[CRUD]] example!
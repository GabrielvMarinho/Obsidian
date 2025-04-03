A guide for [[Java]] Integration with a database

Firstly we have to create a bridge from java to [Sql](obsidian://open?vault=Obsidian&file=Tech%2FDatabase%2FSql%20Databases%2FSql) so that they can communicate, for that, we use [[Drivers]]

Install [MySql](obsidian://open?vault=Obsidian&file=Tech%2FDatabase%2FSql%20Databases%2FMySql) Connector J in [Oracle](obsidian://open?vault=Obsidian&file=Tech%2FProgramming%2FProgramming%20Languages%2FJava%2FOracle)

Open your projects > Project Structure > Libraries > Java > add your jar connector file


### Java code in the DB Class:

```
//last part checks if it exists and creates if not
private final String URL = "jdbc:mysql://localhost:3306/db_sistema_bancario?"+"createDatabaseIfNotExist=true";

private final String USER = "root";  
private final String PASSWORD = "";

public Connection getConnection() throws SQLException {  
    //class - static method to connect to database 
    return DriverManager.getConnection(URL, USER, PASSWORD);  
}
```


Check [[JavaCrudExample]] for a [[CRUD]] example!
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


Check [[JavaCrudExample]] for a [[CRUD]] example!
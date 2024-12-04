### Types of EXECUTE

execute: return true or false
executeUpdate: return how many rows were manipulated (Int)
executeLargeUpdate: return how many rows were manipulated (Long)
executeQuery: return a db query like a select


## Commands

Select:
```
public Cliente create(Cliente cliente){  
    try(Connection con = banco.getConnection()){  
        PreparedStatement ps = con.prepareStatement("""  
                INSERT INTO tb_cliente(nome, cpf) VALUES(?, ?)                """,  
                //especifies that sql has to return the generated primary keys  
                /**you could just put a "1", because the value of  
                 * "Statement.RETURN_GENERATED_KEYS" id "1", it's just                 * an attempt to make it look better                 **/                Statement.RETURN_GENERATED_KEYS);  
        ps.setString(1, cliente.getNome());  
        ps.setString(2, cliente.getCpf());  
        ps.execute();  
        //get the resultSet of the columns of primary keys  
        ResultSet rs = ps.getGeneratedKeys();  
  
        if(rs.next()){  
            cliente.setId(rs.getInt("id"));  
            return cliente;  
        }  
    }catch (SQLException e){  
        e.printStackTrace();  
    }  
    throw new RuntimeException();  
}
```

Insert:
```
public void create(Cliente cliente){  
    try(Connection con = banco.getConnection()){  
        PreparedStatement ps = con.prepareStatement("""  
                INSERT INTO tb_cliente(nome, cpf) VALUES(?, ?)                """, 
                //tells sql to return the primary keys created
                Statement.RETURN_GENERATED_KEYS);  
        ps.setString(1, cliente.getNome());  
        ps.setString(2, cliente.getCpf());  
        ps.execute();  
    }catch (SQLException e){  
        e.printStackTrace();  
    }  
}
```





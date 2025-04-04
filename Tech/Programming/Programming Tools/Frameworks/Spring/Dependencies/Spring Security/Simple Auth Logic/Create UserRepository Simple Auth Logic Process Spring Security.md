we need to create the repository to query the user data

```java
public interface UsuarioDetailsRepository extends JpaRepository<UsuarioDetails, Long> { 
    Optional<UsuarioDetails> findByUsername(String usernam);  
}
```
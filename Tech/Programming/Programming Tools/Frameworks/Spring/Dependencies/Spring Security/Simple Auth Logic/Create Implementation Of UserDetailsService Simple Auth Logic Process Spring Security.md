We need to implement UserDetailsService to create the authmanager bean so spring knows how we will query for the user credentials

```java
@Service  
public class UsuarioAutenticacaoService implements UserDetailsService {  
  
    private final UsuarioDetailsRepository repository;  
  
    @Override  
    public UserDetails loadUserByUsername(String username) throws UsernameNotFoundException {  
  
        return repository  
                .findByUsername(username)  
                .orElseThrow(() -> new UsernameNotFoundException(username));  
    }  
}
```
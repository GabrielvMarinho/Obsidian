Testing the login:
```java
@GetMapping("/user")  
public Object usuarioLogado(HttpServletRequest request){  
    return SecurityContextHolder.getContext().getAuthentication();  
}
```
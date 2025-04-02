
#### SecurityFilterChain Bean

```java
@Bean  
public SecurityFilterChain securityFilterChain(HttpSecurity http) throws Exception {  

    http.authorizeHttpRequests(auth ->{  
        auth.requestMatchers(HttpMethod.POST, "/api/auth/login", "/api/auth/logout").permitAll();  
    });  
    return http.build();  
}
```

#### SecurityFilterChain Bean

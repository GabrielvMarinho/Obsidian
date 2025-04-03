creating the beans

```java
SecurityContextRepository securityContextRepository;  
@Bean  
public SecurityContextRepository securityContextRepository(){  
    if(securityContextRepository == null){  
        securityContextRepository = new HttpSessionSecurityContextRepository();  
    }  
    return securityContextRepository;  
}

//here we are setting the login and logout pages to be accessed by anyone
@Bean  
public SecurityFilterChain securityFilterChain(HttpSecurity http) throws Exception {  
    http.securityContext(config ->config.securityContextRepository(securityContextRepository()));
    http.csrf(AbstractHttpConfigurer::disable);  
    //disabling the default login page
    http.formLogin(AbstractHttpConfigurer::disable);  
        auth.requestMatchers(HttpMethod.POST, "/api/auth/login", "/api/auth/logout")  
        .permitAll()  
		.anyRequest().authenticated();
    });  
    return http.build();  
}
@Bean  
public AuthenticationManager authenticationManager(
        UsuarioAutenticacaoService uds){  
  
    DaoAuthenticationProvider ap = new DaoAuthenticationProvider();  
    ap.setUserDetailsService(uds);  
    ap.setPasswordEncoder(passwordEncoder());  
    return new ProviderManager(ap);  
}
public PasswordEncoder passwordEncoder(){  

    return NoOpPasswordEncoder.getInstance();  

}
```

we are creating the bean of the authentication manager but all the previous providers will be included too.


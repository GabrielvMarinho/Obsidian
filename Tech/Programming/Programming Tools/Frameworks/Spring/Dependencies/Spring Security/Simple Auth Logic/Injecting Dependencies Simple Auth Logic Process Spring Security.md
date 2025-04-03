this would be in the controller:

```java
private SecurityContextRepository secRepository;  

private AuthenticationManager authManager;
```

the depedencies dont have an "auto-inject", meaning the next step is creating the beans
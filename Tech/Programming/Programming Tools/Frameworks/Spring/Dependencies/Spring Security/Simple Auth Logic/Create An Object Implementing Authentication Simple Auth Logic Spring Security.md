In the controller receiving the data we can do so:
```java
Authentication auth = new UsernamePasswordAuthenticationToken(  
        logindto.username(), logindto.password());
```
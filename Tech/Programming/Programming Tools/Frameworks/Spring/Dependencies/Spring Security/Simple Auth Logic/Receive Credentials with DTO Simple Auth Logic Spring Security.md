Heres what the controller is going to look like
```java
@PostMapping("/login")  
@ResponseStatus(HttpStatus.OK)  
public void login(@RequestBody LoginDto logindto,  
                    //auto-mapped  
                    HttpServletRequest request,  
                    HttpServletResponse response){
```

The dto:
```java
  
public record LoginDto (  
        String username,  
        String password  
){  
}
```
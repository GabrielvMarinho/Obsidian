now just save the context in the empty space:
```java
secContext.setAuthentication(auth);  
  
secRepository.saveContext(secContext, request, response);
```
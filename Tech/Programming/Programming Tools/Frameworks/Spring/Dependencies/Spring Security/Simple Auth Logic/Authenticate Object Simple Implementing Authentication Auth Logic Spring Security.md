After creating the object that implements Authentication, we have to authorize it:
```java
auth = authManager.authenticate(auth);
```
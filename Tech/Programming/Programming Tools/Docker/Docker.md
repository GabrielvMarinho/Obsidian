A software development tool that helps bundle the code in images and containers to help standardize the development environment.

[[Docker Image]]

[[Docker Container]]

## Deploying

Dockers can be used to deploy applications, its generally simple to do so in server applications and more of a challenge when it comes to local/desktop applications 



### Example

```dockerfile
FROM openjdk:17-jdk-slim  
  
WORKDIR /spring-app  
  
COPY target/demo-0.0.1-SNAPSHOT.jar app.jar  
  
CMD ["java", "-jar", "app.jar"]
```
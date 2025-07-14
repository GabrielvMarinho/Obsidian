A software development tool that helps bundle the code in images and containers to help standardize the development environment.

## Components 

[[Docker Image]]

[[Docker Container]]
## Environment

Docker runs apps in isolated environments called containers, but unlike [[Virtual Machines]], they share the host's kernel.  
When you write `FROM alpine`, you're using a lightweight Linux-based filesystem without the kernel.  
This makes containers faster and smaller than VMs since they don't virtualize hardware or boot full OSes.  
However, if your host OS (e.g. Windows) doesn't match the container's expected kernel (e.g. Linux), Docker spins up a lightweight VM.  
So while containers aren't VMs by design, kernel mismatch can make Docker rely on one behind the scenes.




## Deploying

Dockers can be used to deploy applications, its generally simple to do so in server applications and more of a challenge when it comes to local/desktop applications 

### Example

```dockerfile
FROM openjdk:17-jdk-slim  
  
WORKDIR /spring-app  
  
COPY target/demo-0.0.1-SNAPSHOT.jar app.jar  
  
CMD ["java", "-jar", "app.jar"]
```
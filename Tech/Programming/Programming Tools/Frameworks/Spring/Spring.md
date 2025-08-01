It's a [[Java]] [[Framework]] that let's you build a full application



example:

```xml
<dependencies>
    <dependency>
        <groupId>org.springframework</groupId>
        <artifactId>spring-webmvc</artifactId>
        <version>5.3.6</version>
    </dependency>

    <dependency>
        <groupId>org.apache.logging.log4j</groupId>
        <artifactId>log4j-slf4j-impl</artifactId>
        <version>2.14.1</version>
    </dependency>

    <dependency>
        <groupId>com.google.code.gson</groupId>
        <artifactId>gson</artifactId>
        <version>2.8.6</version>
    </dependency>

    <dependency>
        <groupId>org.eclipse.jetty</groupId>
        <artifactId>jetty-servlet</artifactId>
        <version>10.0.2</version>
    </dependency>

    <dependency>
        <groupId>org.springframework</groupId>
        <artifactId>spring-jdbc</artifactId>
        <version>5.3.6</version>
    </dependency>

    <dependency>
        <groupId>mysql</groupId>
        <artifactId>mysql-connector-java</artifactId>
        <version>8.0.23</version>
    </dependency>
</dependencies>
```

```java
public class Application {  
   public static void main(String[] args) throws Exception {  
       Server server = new Server();  
       ServerConnector connector = new ServerConnector(server);  
       connector.setPort(8080);  
       server.addConnector(connector);
       ServletContextHandler contextHandler = new ServletContextHandler();  
       AnnotationConfigWebApplicationContext ctx = new AnnotationConfigWebApplicationContext();  
       ctx.register(AppConfig.class);  
       DispatcherServlet dispatcherServlet = new DispatcherServlet(ctx);  
       ServletHolder servletHolder = new ServletHolder("mvc-dispatcher", dispatcherServlet);  
       contextHandler.addServlet(servletHolder, "/*");  
       server.setHandler(contextHandler);  
  
       server.start();  
   }  
}
```
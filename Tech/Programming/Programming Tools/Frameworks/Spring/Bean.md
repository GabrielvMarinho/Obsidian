[[Object]]s that are used in the [[Dependency Injections]] process

examples: @services, @component, etc. Those generates beans automatically, 
The @bean is a bit different, Its used inside a @configuration class and can be used in one of the methods, this gives full controll over what it returns


```java
@Configuration
public class AppConfig {

    @Bean
    public EmailService emailService() {
        return new EmailService(); // manual creation
    }
}
```
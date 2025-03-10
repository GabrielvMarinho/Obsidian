[[Spring]] annotation to manage [[Object]]s

You create a config [[@Configuration]] class that returns an object manipulated by you

if i want to have a custom object of [[ModelMapper]] for example, we can create a bean like this

```java

@Configuration  
public class ModelMapperConfig {  
    @Bean  
    public ModelMapper config(){  
        ModelMapper modelMapper = new ModelMapper();  
        modelMapper.getConfiguration().isSkipNullEnabled();  
        return modelMapper;  
    }  
  
}
```

that way if we construct a service class that has a ModelMapper attribute in it, spring would search to see if there are any beans that returns a model mapper, if so, he will use it
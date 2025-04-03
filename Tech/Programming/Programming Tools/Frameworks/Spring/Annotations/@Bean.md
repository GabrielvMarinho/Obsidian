[[Spring]] annotation to manage [Objects](obsidian://open?vault=Obsidian&file=Tech%2FProgramming%2FProgramming%20Paradigms%2FOOP%2FConcepts%2FObject)

You create a config [[@Configuration]] class that returns an object manipulated by you

if i want to have a custom object of [ModelMapper](obsidian://open?vault=Obsidian&file=Tech%2FProgramming%2FProgramming%20Tools%2FLibraries%2FModelMapper) for example, we can create a bean like this

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
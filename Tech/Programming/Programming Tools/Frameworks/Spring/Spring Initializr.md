
To initialize a [[Spring]] project we can do so

To create an archive go to https://start.spring.io/ 

Project -> [Maeven](obsidian://open?vault=Obsidian&file=Tech%2FProgramming%2FProgramming%20Tools%2FMaeven%2FMaeven)
Language -> Java
Add dependencies -> Spring [Web](obsidian://open?vault=Obsidian&file=Tech%2FSoftware%2FConcepts%2FMISCELLANEOUS%2FWeb)

Class DemoApplication
```
package com.example.demo;  
  
import org.springframework.boot.SpringApplication;  
import org.springframework.boot.autoconfigure.SpringBootApplication;  

//this code creates an http [[Server]]

@SpringBootApplication  
public class DemoApplication {  
  
    public static void main(String[] args) {  
       SpringApplication.run(DemoApplication.class, args);  
    }  
  
}
```

Class Teste
```
package com.example.demo;  
  
import org.springframework.web.bind.annotation.GetMapping;  
import org.springframework.web.bind.annotation.RestController;  

//This code creates and URL "/getDados" that returns a string
//Access http://127.0.0.1:8081/getDados to test the code
@RestController  
public class Teste {  
  
    @GetMapping("/getDados")  
    public String getDados(){  
        return "Serviço funcionando...";  
    }  
}
```

caso as [Ports](obsidian://open?vault=Obsidian&file=Tech%2FSoftware%2FSoftware%20Arquitecture%2FPatterns%20of%20software%2FMicro%20Services%2FPorts) esteja sendo usada, vá para o application.properties:

```
spring.application.name=demo  
server.port=8081
```
assim alteramos a porta para qual escolher

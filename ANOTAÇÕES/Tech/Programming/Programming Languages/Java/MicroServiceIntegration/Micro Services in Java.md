
In [[Java]], we can use Spring to create a web [[Server]] for microservices, an example:

This example is called an [[API REST]]: is called by an URL ([[HTTP]])

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

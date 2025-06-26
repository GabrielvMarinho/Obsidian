A [Maeven](obsidian://open?vault=Obsidian&file=Tech%2FProgramming%2FProgramming%20Tools%2FMaeven%2FMaeven) [Dependency](obsidian://open?vault=Obsidian&file=Tech%2FSoftware%2FSoftware%20Testing%2FJUNIT%2FDependencies) to reduce [Boilerplate Code](obsidian://open?vault=Obsidian&file=Tech%2FProgramming%2FProgramming%20Tools%2FMaeven%2FMaeven) in [[Java]], therefore being very used in [OOP](obsidian://open?vault=Obsidian&file=Tech%2FProgramming%2FProgramming%20Paradigms%2FOOP%2FOOP) [Software](obsidian://open?vault=Obsidian&file=Tech%2FSoftware%2FSofwate%20tools%2FSoftware) development

Helps to keep the code clean.

```java
package com.example.demo.model;  
  
import lombok.*;  
@Data //Basically calls all the notations at class-level  
@Getter  
@Setter //generate all setters, if put in top of the attribute would only make the setter for that attribute  
@RequiredArgsConstructor  
public class Conta {  
    @NonNull  
    @EqualsAndHashCode.Exclude //if a object with the same attribute is instantiated, they will be considered the same  
    private int numero;  
    @NonNull  
    private String titular;  
    @ToString.Exclude //excludes this attribute of the toString  
    private double saldo;  
    private double limite;  
}
```
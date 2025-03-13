How to create simple [[Spring Data JPA]] queries:

in the  jpa [[Interface (Poo)|Interface]] do so:

```java
List<Conta> findByTitular_NomeAndNumero(String nome, Integer numero);
```

1. findByTitular -> will search for the instances in [[@Entity]] Titular
2. _Nome -> will compare the attribute Nome in Titular
3. AndNumero -> adds a new attribute to compara (numero)
4. (String nome, Integer numero) -> the attributes
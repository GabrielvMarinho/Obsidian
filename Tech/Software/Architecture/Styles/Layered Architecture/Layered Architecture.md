A [[Software Architecture]] style.
Divide modules which may be coupled or not in layers.

This is also know as the n-layer architecture style, as the number is not pre-set
most commonly its will be divided in: 
1. Interface layer
2. Bussines layer
3. Persistence layer
4. Database layer

Layered architecture doesn't integrate well with [[Domain Driven Development]] because all the domain features are spread between layers, making it difficult to implement/alter existing domain features;
## Topology: 

![[{F12931AD-1508-415C-A37E-619F777BC762}.png]]
## Example of use:

Any web app
## Rating:

| Architecture characteristic | Star rating |
| --------------------------- | ----------- |
| Partitioning type           | Technical   |
| Number of quanta            | 1           |
| Deployability               | ⭐           |
| Elasticity                  | ⭐           |
| Evolutionary                | ⭐           |
| Fault tolerance             | ⭐           |
| Modularity                  | ⭐           |
| Overall cost                | ⭐⭐⭐⭐⭐       |
| Performance                 | ⭐⭐          |
| Reliability                 | ⭐⭐⭐         |
| Scalability                 | ⭐           |
| Simplicity                  | ⭐⭐⭐⭐⭐       |
| Testability                 | ⭐⭐          |

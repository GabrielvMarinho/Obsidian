A [[Software Architecture]] style.

It's similar to [[Service Based Architecture]] but generally the services are smaller.

The philosophy behind it is: duplication over coupling, each service should cover a bussiness domain workflow separately.

It's not recommended to have a transaction utilize a bunch of different services, as this goes against what microservices represent, if this problem is found, probably the architect was too granular in their design.

## Topology 

![[Pasted image 20251014230727.png]]

## Rating:

| Architecture characteristic | Star rating |
| --------------------------- | ----------- |
| Partitioning type           | Domain      |
| Number of quanta            | 1 to many   |
| Deployability               | ⭐⭐⭐⭐        |
| Elasticity                  | ⭐⭐⭐⭐⭐       |
| Evolutionary                | ⭐⭐⭐⭐⭐       |
| Fault tolerance             | ⭐⭐⭐⭐        |
| Modularity                  | ⭐⭐⭐⭐⭐       |
| Overall cost                | ⭐           |
| Performance                 | ⭐⭐          |
| Reliability                 | ⭐⭐⭐⭐        |
| Scalability                 | ⭐⭐⭐⭐⭐       |
| Simplicity                  | ⭐           |
| Testability                 | ⭐⭐⭐⭐        |
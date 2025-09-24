A [[Software Architecture]] style.

Divided into filters and pipes 
The pipes are for passing data around, generally unidrectional and from a specific point to another
The filters perform a specific task with the data passed

Generally, this would be a [[Monolithic|Monolith]] and would exist to manage operations within a node
## Topology:

![[{0400A790-293C-4CF8-B697-AD94BBD54D64}.png]]
## Example of use:

ETL and EDI
## Rating:

| Architecture characteristic | Star rating |
| --------------------------- | ----------- |
| Partitioning type           | Technical   |
| Number of quanta            | 1           |
| Deployability               | ⭐⭐          |
| Elasticity                  | ⭐           |
| Evolutionary                | ⭐⭐⭐         |
| Fault tolerance             | ⭐           |
| Modularity                  | ⭐⭐⭐         |
| Overall cost                | ⭐⭐⭐⭐⭐       |
| Performance                 | ⭐⭐          |
| Reliability                 | ⭐⭐⭐         |
| Scalability                 | ⭐           |
| Simplicity                  | ⭐⭐⭐⭐⭐       |
| Testability                 | ⭐⭐⭐         |

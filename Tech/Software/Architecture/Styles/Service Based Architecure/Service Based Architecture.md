A [[Software Architecture]] style.

Similar to [[Micro Services]] but has more coarse grained services:
SBA would just create a payment service, while microservices would create a paymentLogin, paymentCatalog, paymentAction, etc.

This more coarse grained presents some tradeoffs:
SBA: more data integrity
Microservices: more testability and deployability
## Topology

![[{F4039BD9-28A8-4607-9ECA-9DDFA8958054}.png]]

## Example of use:

Web apps

## Rating:

| Architecture characteristic | Star rating |
| --------------------------- | ----------- |
| Partitioning type           | Domain      |
| Number of quanta            | 1 to many   |
| Deployability               | ⭐⭐⭐⭐        |
| Elasticity                  | ⭐⭐          |
| Evolutionary                | ⭐⭐⭐         |
| Fault tolerance             | ⭐⭐⭐⭐        |
| Modularity                  | ⭐⭐⭐⭐        |
| Overall cost                | ⭐⭐⭐⭐        |
| Performance                 | ⭐⭐⭐         |
| Reliability                 | ⭐⭐⭐⭐        |
| Scalability                 | ⭐⭐⭐         |
| Simplicity                  | ⭐⭐⭐         |
| Testability                 | ⭐⭐⭐⭐        |
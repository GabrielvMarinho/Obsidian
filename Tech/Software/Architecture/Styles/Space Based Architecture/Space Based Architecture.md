A [[Software Architecture]] style.

the hardest part to scale in a highly demanded web app is the database, this architecture style aims for taking out this bottle neck by replicating the database in in-memory data grids.

processing units: contains the application logic
vvirtualized middleware->
messaging grid:  determines the available processing units for a request and forwards it
data grid: replicate cache of a processing unit
processing grid: optional component that handles the requests in case there is more than one processing units in a single bussiness request
deployment manager: manages the startup and shutdown of processing units instances 
## Topology

![[Pasted image 20251027212714.png]]
## Rating:

| Architecture characteristic | Star rating          |
| --------------------------- | -------------------- |
| Partitioning type           | Domain and technical |
| Number of quanta            | 1 to many            |
| Deployability               | ⭐⭐⭐                  |
| Elasticity                  | ⭐⭐⭐⭐⭐                |
| Evolutionary                | ⭐⭐⭐                  |
| Fault tolerance             | ⭐⭐⭐                  |
| Modularity                  | ⭐⭐⭐                  |
| Overall cost                | ⭐⭐                   |
| Performance                 | ⭐⭐⭐⭐⭐                |
| Reliability                 | ⭐⭐⭐⭐                 |
| Scalability                 | ⭐⭐⭐⭐⭐                |
| Simplicity                  | ⭐                    |
| Testability                 | ⭐                    |
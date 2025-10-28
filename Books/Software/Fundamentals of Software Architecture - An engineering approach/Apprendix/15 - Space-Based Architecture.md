1. Where does space-based architecture get its name from?
- from the tuple space, a technique of using multiple parallel processors communication though shared memory

2. What is a primary aspect of space-based architecture that differentiates it from
other architecture styles?
-  it tries to cut the bottle neck from the root, the database, instead of just scaling everything else or weirdly partitioning the db

3. Name the four components that make up the virtualized middleware within a
space-based architecture.
- messaging grid
- data grid
- processing grid
- deployment manager

4. What is the role of the messaging grid?
- determines the available processing units and forwards the request to them

5. What is the role of a data writer in space-based architecture?
- write the data into the db

6. Under what conditions would a service need to access data through the data
reader?
- a crash, a redeploy or getting data not in the replicated cache

7. Does a small cache size increase or decrease the chances for a data collision?
- increases

8. What is the difference between a replicated cache and a distributed cache? Which
one is typically used in space-based architecture?
- a replicated cache supports a single cache for each processing unit, while a distributed cache is a "separate service"

9. List three of the most strongly supported architecture characteristics in space-
based architecture.
- scalability, elasticity, performance

10. Why does testability rate so low for space-based architecture?
- because testing what this architecture was meant for (thousand concurrent users) is hard to simulate

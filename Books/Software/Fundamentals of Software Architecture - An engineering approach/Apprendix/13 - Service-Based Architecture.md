1. How many services are there in a typical service-based architecture?
- 5-10

2. Do you have to break apart a database in service-based architecture?
- It depends, generally, no

3. Under what circumstances might you want to break apart a database?
- When you need to separate well the services and need to decouple them 

4. What technique can you use to manage database changes within a service-based
architecture?
- replicate the database in memory to another service

5. Do domain services require a container (such as Docker) to run?
- not necessarilly, but it's often the most simple efficient way

6. Which architecture characteristics are well supported by the service-based archi‐
tecture style?
- deployability, testability, reliability 

7. Why isn’t elasticity well supported in a service-based architecture?
- because the services are not very granular, they are coarse grained, which means once you have to quickly scale a services resources you might end up scaling not very used parts

8. How can you increase the number of architecture quanta in a service-based
architecture?
- by creating more module services, even changing to a microservices architecture
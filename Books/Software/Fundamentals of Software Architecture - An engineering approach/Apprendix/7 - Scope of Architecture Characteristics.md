1. What is an architectural quantum, and why is it important to architecture?
- it represents a single deployable component, its important because its a valid and very useful term to talk about software related stuff

2. Assume a system consisting of a single user interface with four independently
deployed services, each containing its own separate database. Would this system
have a single quantum or four quanta? Why?
- four quanta because each service deployed indicates one quanta

3. Assume a system with an administration portion managing static reference data
(such as the product catalog, and warehouse information) and a customer-facing
portion managing the placement of orders. How many quanta should this system
be and why? If you envision multiple quanta, could the admin quantum and
customer-facing quantum share a database? If so, in which quantum would the
database need to reside?
- 2 quanta, it could be in the customer-facing quantum, because the deliverer of content (such as a web api) would have to scale respectively with the database, and it wouldnt make sense to create a service that doesn't need to scale much (warehouse info) with a database that does
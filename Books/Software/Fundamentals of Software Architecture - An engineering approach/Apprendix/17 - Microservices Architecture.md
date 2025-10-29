1. Why is the bounded context concept so critical for microservices architecture?
- because it aligns to its philosophy, maximum decoupling by integrating an entire workflow in each service

2. What are three ways of determining if you have the right level of granularity in a
microservice?
- by purpose, transaction and choreography

3. What functionality might be contained within a sidecar?
- logging related

4. What is the difference between orchestration and choreography? Which does
microservices support? Is one communication style easier in microservices?
-  choreography: follows a workflow and no centrla mediator
- orchestration: managed by a central component
- both are supported orchestration is easier to coordinate a request and maintain observability

5. What is a saga in microservices?
- a service that acts as a mediator when you (rarely) decides that two services should participate in a given worflow

6. Why are agility, testability, and deployability so well supported in microservices?
- since all the services are separated and should be decoupled, this gives the opportunitty for teams to move separately based on the current necessity of changes or improvements of a service

7. What are two reasons performance is usually an issue in microservices?
- network latency and multiple authentication within different services

8. Is microservices a domain-partitioned architecture or a technically partitioned
one?
- domain

9. Describe a topology where a microservices ecosystem might be only a single
quantum.
- when the application itself is small to the point where a nicely granulated service bundles it all

10. How was domain reuse addressed in microservices? How was operational reuse
addressed?
- operational reuse: creating pluggable components or side cars to a service that provides specific functionality like loggin
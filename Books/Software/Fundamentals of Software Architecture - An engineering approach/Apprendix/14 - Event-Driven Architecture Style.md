1. What are the primary differences between the broker and mediator topologies?
- the broker works in a broadcasta fashion, no central mediator, while the mediator provides a central event handler 

2. For better workflow control, would you use the mediator or broker topology?
- the mediator topology, because it gives more control over the state of a specified workflow

3. Does the broker topology usually leverage a publish-and-subscribe model with
topics or a point-to-point model with queues?
- publish subscribe, to decouple producer and subscriber

4. Name two primary advantage of asynchronous communications.
- decoupling
- no request timeouts
- increases reliability (as a service can die for 10 seconds and the queue will still store the request)

5. Give an example of a typical request within the request-based model.
- client requests to server, server digests the requests, server generates a response

6. Give an example of a typical request in an event-based model
- client performs an event, event listener will send the event to be processed by an event processor

7. What is the difference between an initiating event and a processing event in
event-driven architecture?
- the initiating event is something that happens in a listener, trigger ths start of the processing of the event, the processing event is the event representating the digesting of the event

8. What are some of the techniques for preventing data loss when sending and
receiving messages from a queue?
- the mediator topology, greater control over everything in a centralized manner
- asynchronous communication, await for the response
- retries in events in case no answer

9. What are three main driving architecture characteristics for using event-driven
architecture?
- performance, scalability, reliability

10. What are some of the architecture characteristics that are not well supported in
event-driven architecture?
- testability, deployability, simplicity
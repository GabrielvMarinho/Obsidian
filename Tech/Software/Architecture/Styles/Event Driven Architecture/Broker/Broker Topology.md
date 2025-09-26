An [[Event Driven Aarchitecture]] topology

No central event mediator, broadcasting fashion

## Components

1. Initiating event
Starts the entire flow, reacts to an event, like someone placing a bid in an auction system
2. Event broker
A set of channels to pass the event to the event processor
3. Event processor
Receives an event and performs a task
4. Processing event
Event processor will broadcast to the system what happened with something called a processing event.

![[{899EF33E-1BCC-46B3-9D03-7CBCA9570A20}.png]]

## Trade offs

| Advantages                        | Disadvantages        |
| --------------------------------- | -------------------- |
| Highle decoupled event processors | Workflow control     |
| High scalability                  | Error handling       |
| High performance                  | Restart capabilities |
| High fault tolerance              | Data inconsistency   |


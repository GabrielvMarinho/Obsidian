An [[Event Driven Architecture]] topology

A central mediator to handle events

## Components

1. Initiating event
Starts the entire flow, reacts to an event, like someone placing a bid in an auction system
2. Event queue
Stores the initiating events
3. Event mediator
Accepts the initiation event (can have many mediators based on domain features)
4. Event channels
Receives the initiating events when its their turn to be handled
5. Event processors
listen to event channels and process the event

## Topology

![[{CB077131-7785-4373-90F6-3B899B25FDDD}.png]]
## Trade-offs

| Advantages              | Disadvantages                     |
| ----------------------- | --------------------------------- |
| Workflow control        | More coupling of event processors |
| Error handling          | lower salability                  |
| Recoverability          | lower performance                 |
| Restart capabilities    | lower fault tolerance             |
| Better data consistency | modeling complex workflows        |
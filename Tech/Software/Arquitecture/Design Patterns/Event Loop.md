a [[Software]] architecture that manages the execution of code

### Architecture

The event loop is responsible for waiting and dispatching events or messages in a program.
We can say:
#### Event loops dispatches it to an event handler or callback function

#### The callback function invokes a task in the event loop

Walkthrough:

- A program schedules a **task** with an asynchronous API or event source.
    
- The task is handled by a **separate thread, system, or hardware** without blocking the main thread.
    
- The main thread continues executing other code.
    
- When the task is complete, its **callback/event is queued** in the event queue.
    
- The **event loop dequeues and executes** callbacks one by one on the main thread when it’s idle.
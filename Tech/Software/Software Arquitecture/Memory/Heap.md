- Stores data like a [[Tech/Software/Software Arquitecture/Memory/Stack|Stack]] but can be accessed in any order or way
    
- Has more overhead than the stack, naturally
    
- Either reference types (pointers) or value types (there are exceptions)
    
- In async functions, each thread has its own stack
    
    - Each stack is saved temporarily in the heap to be accessed from other stacks
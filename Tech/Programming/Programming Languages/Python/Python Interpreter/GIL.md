Global Interpreter Lock, a mechanism used by [[CPython]] interpreter to assure only one thread in a process executes [[Python]] [[Bytecode]] at a time (some python implementations use it, while others do not).

In some python libraries that are written in C or C++, the GIL might already be unlocked. 

## Should it be unlocked?

Sometimes it makes sense to unlock the GIL.
When we are talking about computing/scientific computing, just using different processes is not a suitable alternative, in these situations, the realease of the GIL is necessary.

### Are there workarounds?

The current workarounds for developing without unlocking the GIL are complex to maintain.

For example, you might start multiple processes to a task, this would require some sort of [[IPC]], which not only makes it complex to handle this "bridge" that needs to be created from one process to another, it also adds overhead. 

So sometimes, its better to unlock it.
talks about memory management in general

how even modern languages with garbage collectors can lead to memory leaks, as a [[Garbage Collector]] will never deleted a content with a reference

touches [[Memory leaks]], [[Dangling pointer]]


## There are levels to this thing

there are levels to managing memory, once a program exits, the [[Operating System]] will get all the memory allocated for the heap, code, stack, etc. and just claim it, so generally a memory leak within a process wont cause operating system issues, though its great to notice that it gets more complex with applications like long running web servers, database management system, etc.
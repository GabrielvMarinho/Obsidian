A running instance of a program, may contain multiple [[Thread|Threads]]


## Initializing a process

The process of initializing a [[Process]] looks like this:

1. Load the file and static assets from disk to memory
2. run the program
3. switch from running, ready or blocked status at runtime

the process switches from those status based on if its using the [[CPU]] or not, like in a I/O situation
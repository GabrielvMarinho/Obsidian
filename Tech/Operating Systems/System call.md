A form of exposing functionalities to the user program such as killing and creating processes

in a OS you can be in:
user mode: access to basic stuff
kernel mode: can do the amazing stuff like killing processes

To make a system call the user needs to run a trap instruction, which briefly turns the user mode to kernel mode, to execute some functionality

1. A sofware [[Trap instruction]] happens (system call is made) 
	 
2. cpu switches from user mode to kernel mode
	
3. after finding the instruction and executing it, the cpu gets back to user mode


### System call ID

each system call has an ID:

```
marinho@time-machine:~/$ ausyscall --dump
Using x86_64 syscall table:
0	read
1	write
2	open
3	close
4	stat
...
```

each call then corresponds to a code chunk (this is redirected by the [[Trap table]])
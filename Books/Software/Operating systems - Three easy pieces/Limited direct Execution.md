## Restricted operations

This is dealt by switching the program from kernel mode to user mode whenever necessary, it uses [[System call]]s and [[Trap table]]s to ensure safety

## Switching between processes

An [[Operating System]] cant do anything if a program is running on the [[CPU]], how does it gain access over the cpu to then switch to another process?

the solution is a [[Timer Interrupt]]
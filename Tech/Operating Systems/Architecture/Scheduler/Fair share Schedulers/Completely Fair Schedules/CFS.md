Completely fair scheduler 
a [[Fair share schedulers|Fair share scheduler]] approach

Focus on speding less time deciding which process to run next, increasing performance with the con of distributing it not so well (aka adjusting to IO and responsive applications).

to divide the time slices the cfs use a concept called virtual runtime

as a [[Process]] runs it accumulates virtual runtime, generally proportionally to the physical time.
the next process will always be the one with the least virtual runtime

stores the systems running processes virtual runtimes in a [[Red-black tree]]
### Niceness

cfs enable a system of niceness, the nicer a process is, the more likely it is to let another process use its time, if you have a not so nice program, it means it has priority

### Long sleeping processes

for long sleeping process like 10s, the process would monopolize the [[CPU]] after waking up, cfs solves this by giving the waking process the lowest virtual runtime existant in the data structure storing all the virtual runtime of running processes, that way, avoiding  starvation of other processes
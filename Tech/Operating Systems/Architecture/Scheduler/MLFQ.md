Multi level feedback queue.
A [[CPU]] [[Scheduler]] algorithm prioritizes processes based on past behaviour.

It's implementations follow similar rules, though they may vary on some specifics.

The system is divided in queues, those are the rules:
## The rules
1. if priority(a) > priority(b), A runs
2. if priority(a) = priority(b), A & B runs in Round Robin
3. when a job enters the system, it is placed at the highest queue
4. a - if a job uses up an entire time slice while running, its priority is reduced to a lower queue
`4`. b - if a job gives up the cpu before the time slice is up, it stays at the same priority level

this brings some problems ->
1. starvation of long running processes
2. a cpu bound process can become a interactive job (which is now running at a very low level queue)
3. a user could use 99% of the time slice and issue an IO at the last microsecond, giving him priority, a trick to monopolize the CPU

a new rule from it:
5. after some period of time increase priority of all processes to the topmost queue
this solves the cpu bound and interactive process problem as well as the starvation one

now to solve the user 99% problem we can rewrite 4a and 4b to a single rule
4. Once a job uses up its time allotmen at a given level (regardless of how many times it has given up the CPU), its priority is reduced (moves down one queue).


## Parameters
when implementing a MLFQ you have to se some parameters like:
1. lenght of time slice per queue
2. how often should priority be boosted (rule 5)



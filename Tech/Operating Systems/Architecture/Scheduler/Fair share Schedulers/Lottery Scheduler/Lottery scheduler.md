a [[Fair share schedulers|Fair share scheduler]] approach

each [[Process]] has it's number of tickets (e.g. process "x" has 10 tickets)
the scheduler has a number of total tickets (e.g. 100)

The scheduler will then generate a random number to then decide which process should run next, for example, if we have 10 processes with 10 tickets and the total tickets was 100, intuitively the chance of a specific process running would be 10%. 

### Ticket assigning 

the approach is environment-dependent
if the cpu has processes that can trust each other -> let them inflate and deflate their ticket count
if the cpu has processes that cannot trust each other -> the cpu has to assign the ticket count

### Fairness

The longer a job runs, the more likely it is to be fairly scheduled, the fairness of a program is calculated by divinding the time the first job ends to the second's.

If job 1 ends at 10 and job 2 ends at 20, the fairness metric will be 10/20=0.5.

check:
[[Lottery scheduler chart]]





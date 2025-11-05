a [[Fair share schedulers|Fair share scheduler]] approach

similar to [[Lottery scheduler]] approach, but it provides a deterministic approach

each process has a stride that increments a count

1. give each [[Process]] a stride 
2. runs the process with the lowest count
3. each time you run a process increment the stride to the count

an example to this approach might look like this:

| A   | B   | C   | Who Runs? |
| --- | --- | --- | --------- |
| 0   | 0   | 0   | A         |
| 100 | 0   | 0   | B         |
| 100 | 200 | 0   | C         |
| 100 | 200 | 40  | C         |
| 100 | 200 | 80  | C         |
| 100 | 200 | 120 | A         |
| 200 | 200 | 120 | C         |
| 200 | 200 | 160 | C         |
| 200 | 200 | 200 | ...       |
this lowers the level of unfairness which is found in the [[Lottery scheduler]], however this is a less maleable environment to add new processes for example (it would have to start at 0 and would monopolize the cpu)
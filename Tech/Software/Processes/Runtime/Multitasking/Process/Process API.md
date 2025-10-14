Every [[Operating System]] will expose an [[API]] to manage [[Process|Processes]].

it might look like this:
1. fork() -> creates a new process within an existing one, continuos a "branch" of execution with its own space in memory and pid.
2. wait() -> wait for something, like the parent wait for the forked child to execute.

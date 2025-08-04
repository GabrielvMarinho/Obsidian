[[Python]] module from standarts libreary to spawn separate processes, with individual interpreters and memory space for python only


pickle means serialize -> python tries to pickle the process and pass to the child

### Start_method()

you can set the start method for the multiprocesses, the key differences are:
1. spawn: new python interpreter
2. fork: the new process is a fork of the parent
3. forkserver: a server process is started
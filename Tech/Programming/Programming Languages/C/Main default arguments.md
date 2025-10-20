the default arguments for a main function in [[C]] are:

1. `int argc`:  sets the size of the argv array
2. `char *argv[]`: the arguments passed to the function

example of arguments:
```
argc -----
gc -> 1
argv -----
argv 0 ->./test
argv 1 ->(null)
argv 2 ->SHELL=/bin/bash
argv 3 ->SESSION_MANAGER=local/time-machine:@/tmp/.ICE-unix/3914,unix/time-machine:/tmp/.ICE-unix/3914
```
in this case there is only one argv, if you keep trying to iterate through it youll start accessing the environment variables.


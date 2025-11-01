Mechanisms to share data within processes ([[IPC]]), unidirectly.
A pipe consists of a write [[File descriptor]] and a read [[File descriptor]].
You use the writer to write and the reader to read.
Its all saved in memory and the content expires once a process reads it.


```c
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
#include <string.h>
#include <sys/wait.h>

int main(void){
        int fds[2];
        pipe(fds);
        if(fork()==0){
                write(fds[1], "msg\0", 3);
        }
        else{
                wait(NULL);
                char buffer[3];
                read(fds[0], buffer, 3);
                printf("the buffer written is %s", buffer);
        }

}
```

this example shows the communication of two processes with a pipe mechanism

## Named pipes

named pipes are similarly to normal (unnamed) pipes, the difference is that they persist on disk




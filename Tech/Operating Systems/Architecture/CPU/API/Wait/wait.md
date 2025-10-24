[[CPU]] method that awaits for a forked process to finish

```c
#include <stdio.h>
#include <unistd.h>
#include <sys/wait.h>

int main(int argc, char *argv[]){
        printf("parent -> %d\n", getpid());
        int pid = fork();
        if(pid==0){
                printf("hello %d\n", getpid());
        }else if (pid>0){
                int x = wait(NULL);
                printf("%d", x);
                printf("goodbye %d\n", getpid());
        }
        return 0;
}

```

the parent waits so that the child prints the `hello` first, then returning the pid in the value of x
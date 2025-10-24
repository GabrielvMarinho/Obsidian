[[CPU]] method that awaits for a specific process to finish

```c
#include <stdio.h>
#include <unistd.h>
#include <sys/wait.h>

int main(int argc, char *argv[]){
        printf("parent -> %d\n", getpid());
        int pid0 = fork();
        
        if(pid0==0){
                printf("hello from child 0 %d\n", getpid());
        }else if (pid0>0){
                int x = waitpid(pid0, NULL, 0);
                printf("%d", x);
                printf("i just waited for the child 0 %d\n", getpid());
        }
        return 0;
}
```

With waitpid you can have more control and wait for specific process (which will be identified with the pid) to finish.
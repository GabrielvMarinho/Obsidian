```c
#include <stdio.h>
#include <unistd.h>

int main(int argc, char *argv[]){
	printf("parent %d\n", getpid());
	int pid = fork();
	if(pid==0){
		printf("child %d\n", getpid());
		char myargs[0];
		execl("/bin/ls", "program_name", NULL);
		printf("i will never be printed");
	}else if(pid>0){
		printf("parent again %d\n", getpid());
	}
	
}
```

The child process is replaced by the ls process
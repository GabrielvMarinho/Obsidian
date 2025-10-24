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


## Why so many execxx?

They primarily do the same thing, spawn processes from the executing one.

They have differences related to environment and paramaters, as state next:

|Function|How command + args are passed|How environment is handled|Notes|
|---|---|---|---|
|`execl(path, arg0, arg1, ..., NULL)`|Argument list (variadic)|Inherits current env|You list args explicitly.|
|`execle(path, arg0, arg1, ..., NULL, envp)`|Argument list (variadic)|**Explicit env** provided (`envp`)|`envp` = `char *envp[]`.|
|`execlp(file, arg0, arg1, ..., NULL)`|Argument list (variadic)|Inherits current env|`p` → searches `PATH` for the file.|
|`execv(path, argv)`|Argument **array** (`char *argv[]`)|Inherits current env|Convenient when args are in an array.|
|`execve(path, argv, envp)`|Argument array|**Explicit env** provided (`envp`)|**System call** — the base form; others are wrappers.|
|`execvp(file, argv)`|Argument array|Inherits current env|`p` → searches `PATH`.|
|`execvpe(file, argv, envp)`|Argument array|**Explicit env** provided|`p` → searches `PATH`; not in POSIX but common (glibc).|

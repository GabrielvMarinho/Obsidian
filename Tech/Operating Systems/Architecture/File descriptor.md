an integer number that identifies a specific file/socket in the kernel

each open file has a file descriptor managed by the [[Kernel]], its process dependent and private, not a global table

```c
#include <stdio.h>
#include <fcntl.h>

int main(void){
	int fds = open("file.txt", O_CREAT | O_RDWR);
	printf("the file descriptor is %d\n", fds);

}
```
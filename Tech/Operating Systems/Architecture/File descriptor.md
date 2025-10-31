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

you could then call something like a `write(fds, "hi", 2)` 

just opening a file doesnt actually load anything into memory, just holds metadata as the location of the file, calling write and read operations is when the operating system may load it.
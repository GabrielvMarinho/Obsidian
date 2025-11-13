the main components of a program is code, the stack and the heap.

this shows a visualization
```c
#include <stdio.h>
#include <stdlib.h>

int main(void){
	printf("location of code: %p\n", (void *) main);
	printf("locationb of heap: %p\n", (void *) malloc(1));
	int x = 3;
	printf("location of stack: %p\n", (void *) &x);
	return x;
}
```

first the location of the code is static therefore it is the first stored component in memory from the program, then comes the heap which is "right below it" in the virtual memory, the [[Heap]] grows downwards, its given some space and you have the [[Tech/Operating Systems/Architecture/Memory/Stack|Stack]], which grows upwards.


![[Address space.png]]
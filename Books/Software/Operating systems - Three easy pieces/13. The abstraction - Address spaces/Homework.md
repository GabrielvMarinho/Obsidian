in the homework it was asked to make a program that allocates a certain amount of megabytes to see the diff in the `free` cmd function

i came up with this:

```c
#include <stdio.h>
#include <stdlib.h>
int main(int argc, char *argv[]){
        int array_size = atoi(argv[1]);
        size_t array_size_byte = array_size *1024 *1024;
        char *p = malloc(array_size_byte);
        for(int i=0; i<array_size_byte; i++){
                p[i] = '1';
        }
        while(1){

        }
}
          
```

this allocates some memory on the heap and the change in free memory is very clear.

also used pmap to list the memory mapping of processes
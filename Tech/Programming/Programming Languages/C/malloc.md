Memory ALLOCation function in [[C]], a library that implements [[System call]]s under the hood, used to memory allocate in the [[Heap]]

```c
#include <stdlib.h>

int main(void){
        int *x = malloc(sizeof(int));
}
```

this allocates a total of 4 bytes (integer size) and returns a pointer ([[Memory Address]]) to those bytes that is allocated on the [[Tech/Operating Systems/Architecture/Memory/Stack|Stack]] with x

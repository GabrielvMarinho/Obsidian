allocating data on the [[Tech/Operating Systems/Architecture/Memory/Stack|Stack]]
```c
int main(void){
	int x;
}
```

allocating data on the [[Heap]] (also on the stack to save the pointer)
```c
#include <stdlib.h>

int main(void){
        int *x = (int *) malloc (sizeof(int));
}
```

explains [[malloc]], [[free]] more deeply
undefined behaviour example:

```c
void main(void){
        int *array = malloc(sizeof(int)*10);
        array[5] = 5;
        printf("%d", array[5]);
        free(array);
        printf("%d", array[5]);
}
```

the memory is freed, so you cont own it anymore, the value still might read as 5, but this is not guaranteed, as another thread within the process can use it, just like in memory in general, after freeing something doesn't necessarily means you lost it completely, just lost the pointer.
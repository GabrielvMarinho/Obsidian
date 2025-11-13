a call to free [[Heap]] allocated bytes
```c
int *x = malloc(sizeof(int));
free(x);
```

modern [[Operating System]]s and [[Garbage Collector]]s in high level langs, automatically free [[Heap]] data that is not freed when the program ends, however It's considered bad practice to do so (in the operating system context, of course you cant even choose this with GCs).
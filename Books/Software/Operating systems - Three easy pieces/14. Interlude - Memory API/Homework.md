homework talked about memory allocation and some tools for visualization for example valgrind:

```c
#include <stdlib.h>
#include <stdio.h>
void main(void){
        int *data = malloc(sizeof(int)*100);
        data[99] = 0;
        printf("%d", data[99]);
}
```

running this with `valgrind --leak-check=yes ./array` outputs:

```
==217539== Memcheck, a memory error detector
==217539== Copyright (C) 2002-2022, and GNU GPL'd, by Julian Seward et al.
==217539== Using Valgrind-3.22.0 and LibVEX; rerun with -h for copyright info
==217539== Command: ./array
==217539== 
0==217539== 
==217539== HEAP SUMMARY:
==217539==     in use at exit: 400 bytes in 1 blocks
==217539==   total heap usage: 2 allocs, 1 frees, 1,424 bytes allocated
==217539== 
==217539== 400 bytes in 1 blocks are definitely lost in loss record 1 of 1
==217539==    at 0x4846828: malloc (in /usr/libexec/valgrind/vgpreload_memcheck-amd64-linux.so)
==217539==    by 0x10917E: main (in /home/marinho/Documents/studying/ostep/random/array)
==217539== 
==217539== LEAK SUMMARY:
==217539==    definitely lost: 400 bytes in 1 blocks
==217539==    indirectly lost: 0 bytes in 0 blocks
==217539==      possibly lost: 0 bytes in 0 blocks
==217539==    still reachable: 0 bytes in 0 blocks
==217539==         suppressed: 0 bytes in 0 blocks
==217539== 
==217539== For lists of detected and suppressed errors, rerun with: -s
==217539== ERROR SUMMARY: 1 errors from 1 contexts (suppressed: 0 from 0)
```
no issues (i guess)

now running when trying to write to an array position that wasn't allocated, like 100, it outputs this: 

```
==217499== Memcheck, a memory error detector
==217499== Copyright (C) 2002-2022, and GNU GPL'd, by Julian Seward et al.
==217499== Using Valgrind-3.22.0 and LibVEX; rerun with -h for copyright info
==217499== Command: ./array
==217499== 
==217499== Invalid write of size 4
==217499==    at 0x10918D: main (in /home/marinho/Documents/studying/ostep/random/array)
==217499==  Address 0x4a801d0 is 0 bytes after a block of size 400 alloc'd
==217499==    at 0x4846828: malloc (in /usr/libexec/valgrind/vgpreload_memcheck-amd64-linux.so)
==217499==    by 0x10917E: main (in /home/marinho/Documents/studying/ostep/random/array)
==217499== 
==217499== Invalid read of size 4
==217499==    at 0x10919D: main (in /home/marinho/Documents/studying/ostep/random/array)
==217499==  Address 0x4a801d0 is 0 bytes after a block of size 400 alloc'd
==217499==    at 0x4846828: malloc (in /usr/libexec/valgrind/vgpreload_memcheck-amd64-linux.so)
==217499==    by 0x10917E: main (in /home/marinho/Documents/studying/ostep/random/array)
==217499== 
0==217499== 
==217499== HEAP SUMMARY:
==217499==     in use at exit: 400 bytes in 1 blocks
==217499==   total heap usage: 2 allocs, 1 frees, 1,424 bytes allocated
==217499== 
==217499== 400 bytes in 1 blocks are definitely lost in loss record 1 of 1
==217499==    at 0x4846828: malloc (in /usr/libexec/valgrind/vgpreload_memcheck-amd64-linux.so)
==217499==    by 0x10917E: main (in /home/marinho/Documents/studying/ostep/random/array)
==217499== 
==217499== LEAK SUMMARY:
==217499==    definitely lost: 400 bytes in 1 blocks
==217499==    indirectly lost: 0 bytes in 0 blocks
==217499==      possibly lost: 0 bytes in 0 blocks
==217499==    still reachable: 0 bytes in 0 blocks
==217499==         suppressed: 0 bytes in 0 blocks
==217499== 
==217499== For lists of detected and suppressed errors, rerun with: -s
==217499== ERROR SUMMARY: 3 errors from 3 contexts (suppressed: 0 from 0)
```
which display bad things, i guess


talked about [[dgb]] and [[valgrind]]
the time to make a system call is approximatelly 3 micro seconds.

```c
#include <stdio.h>
#include <sys/time.h>
#include <unistd.h>

int main(void){
        struct timeval tv;
        gettimeofday(&tv, NULL);
        printf("%ld.%06ld\n", tv.tv_sec, tv.tv_usec);
        for(int i=0;i<1000000;i++){
                read(0, NULL, 0);
        }
        struct timeval new_tv;
        gettimeofday(&new_tv, NULL);
        double elapsed = (new_tv.tv_sec - tv.tv_sec) +
                     (new_tv.tv_usec - tv.tv_usec) / 1e6;

        printf("The time to make 1,000,000 system calls is %.6f seconds\n", elapsed);


}
```

dividing it for 1.000.000 you get the average time to make a system call, approximatelly

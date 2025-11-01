a context switch takes some micro seconds
```c
#include <stdio.h>
#include <unistd.h>
#include <sys/time.h>

int main(void){
		
	struct timeval old_tv;
        gettimeofday(&old_tv, NULL);

	for(int i=0; i<10000; i++){
		sleep(0);
	}
	struct timeval new_tv;
        gettimeofday(&new_tv, NULL);
        double elapsed = (new_tv.tv_sec - old_tv.tv_sec) +
                     (new_tv.tv_usec - old_tv.tv_usec) / 1e6;	
	printf("the time to run 10k context switches is %f", elapsed);
}
```

this is giving me 50 microseconds approximatelly but i heard system calls dont actually cause a full context switch.'
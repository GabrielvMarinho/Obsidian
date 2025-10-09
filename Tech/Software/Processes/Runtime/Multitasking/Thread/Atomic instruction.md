An atomic instruction is something that can surely be started and finished without redirecting processing power to another thread's tasks within a concurrent environment, if a function needs to get an input, fetch an api and process the data, chances are, if you are working with threads, and this function is running, a new thread will "steal" the cpu processing power (while it was going to process the data for example), to run concurrently, of course. This can lead to unexpected behavior:

```c
#include <stdio.h>
#include <stdlib.h>
#include "common.h"
#include "common_threads.h"

volatile int counter = 0;
int loops;

void *worker(void *arg){
	int i;
	for(i =0 ; i<loops; i++){
		counter++;
	}
	return NULL;
}
int main(int argc, char *argv[]){
	if(argc !=2){
		fprintf(stderr, "usage: threads <loops>\n");
		exit(1);
	}
	loops = atoi(argv[1]);
	pthread_t p1, p2;
	printf("initial value: %d\n", counter);
	Pthread_create(&p1, NULL, worker, NULL);
	Pthread_create(&p2, NULL, worker, NULL);
	Pthread_join(p1, NULL);
	Pthread_join(p2, NULL);
	printf("final value: %d\n", counter);
	return 0;

}
```

./mem 1000
will result in normal behaviour (2000), but larger numbers will change expected value, like: 

./mem 100000

So instead of 200000 it will have a different value, like 123208

Thea reason for this is because the action of incrementing the counter is not atomic, it needs to:
1. load the value of the counter from memory into a register
2. increment it
3. store back in memory

while thread 1 is just done incrementing, thread 2 can come and load the old value, before it can be saved by thread 1, creating this weird behaviour.
A [[Python]] module used to run multiple [[Thread]]s concurrently within a single [[Process]].

A new Thread is really created, but because of [[GIL]], only one of them run python byte code at a time, the sequence of execution is decided by a [[Scheduling algorithms|scheduling algorithm]].

Specifics:
- Can execute tasks in parallel.
- Shared memory space.

```python
import threading
import time

def crawl(link, delay=3):
    print(f"crawl started for {link}")
    time.sleep(delay)  # Blocking I/O (simulating a network request)
    print(f"crawl ended for {link}")

links = [
    "https://python.org",
    "https://docs.python.org",
    "https://peps.python.org",
]

# Start threads for each link
threads = []
for link in links:
    # Using `args` to pass positional arguments and `kwargs` for keyword arguments
    t = threading.Thread(target=crawl, args=(link,), kwargs={"delay": 2})
    threads.append(t)

for t in threads:
    t.start()

# Wait for all threads to finish
for t in threads:
    t.join()
```

An example with shared memory:
```python

import threading

# Shared memory
counter = 0
counter_lock = threading.Lock()

# Worker function
def increment():
    global counter
    for _ in range(100000):
        # Acquire lock before modifying shared memory
        with counter_lock:
            counter += 1

# Create threads
thread1 = threading.Thread(target=increment)
thread2 = threading.Thread(target=increment)

# Start threads
thread1.start()
thread2.start()

# Wait for threads to finish
thread1.join()
thread2.join()

print(f"Final counter value: {counter}")
```
The lock provided a way to avoid concurrency.

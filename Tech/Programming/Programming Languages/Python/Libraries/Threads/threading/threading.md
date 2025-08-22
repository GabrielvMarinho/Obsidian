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


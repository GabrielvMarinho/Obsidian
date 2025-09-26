A programming model where tasks can start, pause, and resume without blocking the entire flow — allowing other tasks to run [[Concurrency|Concurrently]] without waiting (generally in the same thread).



## Example:

```python
import asyncio

async def task(n):
    print(f"Start {n}")
    await asyncio.sleep(1)  # simulates I/O
    print(f"End {n}")

async def main():
    await asyncio.gather(task(0), task(1), task(2))

asyncio.run(main())
```

This creates an [[Event Loop]].
When the `await asyncio.sleep(1)` is reached, it goes to the next task.
internally its like there is a callback to be called when its finished to print the "End".

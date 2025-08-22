A [[Python]] module used to create specifically multiple python interpreter [[Process|Processes]], bypassing the [[GIL]].

```python
from multiprocessing import Process

def f(name):
    print('hello', name)

if __name__ == '__main__':
    p = Process(target=f, args=('bob',))
    p.start()
    p.join()
```
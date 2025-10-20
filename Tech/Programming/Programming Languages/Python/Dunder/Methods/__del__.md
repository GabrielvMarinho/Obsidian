[[Python]] [[Dunder]] method.

called before an object is about to be destroyed.

```python
class Test():
    def __del__(self,):
        print("this is about to be destroyed")

test = Test()
del test

```

ouptut:
```
this is about to be destroyed
```
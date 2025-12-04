[[Python]] [[Dunder]] method.
makes an object callable.
when you call an object() the compiler translates to obj.`__call__`()
```python
class Testing():
    def __call__(self):
        print("Object is callable")
        
test = Testing()
test()
```

output:
```
Object is callable
```

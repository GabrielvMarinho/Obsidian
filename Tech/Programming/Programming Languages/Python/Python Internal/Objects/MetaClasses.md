define how [[Classes]] behave

```python
class MyMeta(type):
    def __new__(cls, name, bases, clsdict):
        clsdict["show"] = lambda self: "hello from metaclass"
        return super().__new__(cls, name, bases, clsdict)

class MyClass(metaclass=MyMeta):
    pass

m = MyClass()

print(m.show())
```

generally used in framework/library/complex cases
functions used to create [[Iterator|Iterators]], returns an iterable set of items, on item at a time, the yield command is used for that.

generator implement the `__next__` and `__iter__` methods

Example:
```python
def fibonacci():
    a = 0
    b = 1
    while True:
        temp = b
        b = b+a
        a = temp
        yield a
iterableSet = fibonacci()
print(next(iterableSet))
print(next(iterableSet))
print(next(iterableSet))
print(next(iterableSet))
print(next(iterableSet))
print(next(iterableSet))
print(next(iterableSet))
```

Output:
```cmd
1
1
2
3
5
8
13
```

Only a python implemented function can be a generator, c built in functions cant.


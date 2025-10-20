a [[Python]] obj type

they over-allocate memory in order to make append functions run more efficiently:

```python
>>> sys.getsizeof(tuple(range(10)))
128
>>> sys.getsizeof(list(range(10)))
136
```

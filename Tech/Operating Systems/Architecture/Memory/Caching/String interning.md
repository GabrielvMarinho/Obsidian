[[Caching]] mechanism to save memory in allocating space to strings

```python
>>> x = "string"
>>> y = "string
>>> id(x) == id(y)
```
when strings are "simple" or are not dynamically created, a language like [[Python]] will utilize string interning to give the same memory space to both variables, then just point to it

```python
>>> x = "complex not simple string!"
>>> y = "complex not simple string!"
>>> id(x) == id(y)
False
```

in this example the string is not simple, making it not share the same location
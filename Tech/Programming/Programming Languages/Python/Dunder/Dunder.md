Simply stands for double underscores.

Also related as [[Python]] magic

You can call them in different ways:
```
print(repr(a))
print(a.__repr__())
```

The first way will work and call the fallback from object, while the other will throw when not found


## Don't call it though

You should define dunder methods in classes, but shouldnt call them, its usually best to let it be used by python internal functions. You don't ever call `__len__`, you call len(), which then calls `__len__`
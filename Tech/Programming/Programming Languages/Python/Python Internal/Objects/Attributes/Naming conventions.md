in [[Python]], the name convention for attributes is:

### Single underscore

```python
class Test:
	def __init__(self):
		self._name = "name"
```

in this case, this indicates that the attribute is private, therefore shouldn't be used outside the own class implementation, it can be used though, just shouldn't

### Double underscore

```python
class Test:
	def __init__(self):
		self.___name = "name"
```

used to indicate a python magic attribute or utilize the [[Name mangling]] functionality of the python interpreter
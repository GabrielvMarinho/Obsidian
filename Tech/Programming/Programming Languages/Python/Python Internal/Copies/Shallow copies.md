if you attribute a var to another var, they might point to the same object in memory

```python
x = [1, 2]
y = x
y.pop()
print(x)
print(y) 
```
output:
```shell
[1]
[1]
```

shallow copy will solve this problem

```python
import copy
x = [1, 2]
y = copy.copy(x)
y.pop()
print(x)
print(y) 
```
output:
```shell
[1, 2]
[1]
```

it doesnt solve the problem if you have nested objects, shallow copy only copies the main object, to create a whole new obj see [[Deep copies]]

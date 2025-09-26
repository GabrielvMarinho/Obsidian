Is used to copy independent nested objects to a variable:

```python
import copy
x = [[1, 2], [3, 4]]
y = copy.deepcopy(x)
y[0].pop()
print(x)
print(y) 
```
output:
```shell
[[1, 2], [3, 4]]
[[1], [3, 4]]
```

It recursively checks for internal objects and make a copy as well
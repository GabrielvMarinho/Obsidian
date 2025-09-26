[[Python]]'s management system utilized reference counting to decide if a memory space can be [[Garbage Collector|Garbage collected]] 

```
import ctypes

my_list = [1, 2, 3]


address = id(my_list)

ref_count = ctypes.c_long.from_address(address).value

print(ref_count)
```
output:
```
1
```

if we delete the reference the space will be garbage collected:
```
del my_list
print(ctypes.cast(address, ctypes.py_object).value)
```
output:
```
[]
```
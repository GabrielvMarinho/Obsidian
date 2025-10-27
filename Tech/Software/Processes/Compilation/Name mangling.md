a process in code [[Compiler|Compilation]] that changes the name of a class attribute to not overload the name:


```python
class A:
    def __init__(self): 
	    self.__x = 1

a = A()
print(a._A__x)  # 1
```

A [[Python]] function being called by the instance of a class, the method is """bound""", or also, pointing to the class function, because all the functions are stored in the class, not the instances

When you call it, it automatically sends the instance as a paremeter, self.

```python
x = 5.5
x.is_integer()
float.is_integer(x)
```

both will work, under the hood python injects the x as the self parameter when nothing is passed.

bound method in practice:
```python
class User:
	def user_function(self):
	    print("this is a function")


print(User.user_function)
user = User()
print(user.user_function)
```

output:
```cmd
<function User.user_function at 0x000001BD67030040>
<bound method User.user_function of <__main__.User object at 0x000001BD67048440>>
```

notice how the instance just points to the class function

## Internal Methods

In internal classes its a bit different because methods are defined at C level

```cmd
>>> x = 5
>>> int.bit_count
<method 'bit_count' of 'int' objects>
>>> x.bit_count
<built-in method bit_count of int object at 0x00007FFABDBB2428>
```
technically the x.bit_count is also a bound method
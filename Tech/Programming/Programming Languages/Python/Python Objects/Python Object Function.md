A [[Python]] object's attributes can be accessed through `obj.__dict__`. These attributes are all objects themselves, so you can assign a function as one of them. That’s why the first parameter of a method is `self` — without it, the function wouldn’t know anything about the instance’s state because it would be detached.

The `__dict__` of an instance stores its own attributes in a dictionary. Normal attributes are stored independently, but function attributes actually point to the class’s function in the class’s `__dict__`.

The class’s `__dict__` is a **mappingproxy**, which acts as a read-only view of the class’s attributes.

So, attributes like functions are shared among all instances, while instance attributes live separately in each object’s own `__dict__`.

## Example

code:
```python
class User:
	def user_function(self):
	    print("this is a function")

print(User)
print(User.user_function)
user = User()
print(user.user_function)
```

output:
```cmd
<class '__main__.User'>
<function User.user_function at 0x000001BD67030040>
<bound method User.user_function of <__main__.User object at 0x000001BD67048440>>
```

notice how the class instance is just a [[Bound method]] pointing to the original address of the class function.
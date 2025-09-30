extend behaviour or functions and methods without changing their actual code in [[Python]]

Example: 
```python
def decorator(func):
    def wrapper():
        print("Before calling the function.")
        func()
        print("After calling the function.")
    return wrapper

@decorator
def greet():
    print("Hello, World!")
greet()
```

in old python syntax (<2.4)

```python
def decorator(func):
    def wrapper():
        print("Before calling the function.")
        func()
        print("After calling the function.")
    return wrapper

def greet():
    print("Hello, World!")

greet = decorator(greet)
greet()
```
specific type of parameters in [[Python]] to use when uncertain behavior is expected.

Example:
```python
def args_function(*args):
    print(args)
def kwargs_function(**kwargs):
    print(kwargs)

args_function("hey", "bye")
kwargs_function(greeting="hey", not_greeting="bye")
```

Output:
```
('hey', 'bye')
{'greeting': 'hey', 'not_greeting': 'bye'}
```
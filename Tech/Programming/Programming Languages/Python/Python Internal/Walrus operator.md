introduced on version 3.8, operator to assign a variable within an expression in [[Python]]:

before
```python
line = file.readline()
while line:
    process(line)
    line = file.readline()

```
after
```python
while (line := file.readline()):
    process(line)
```

the walrus operator can have performance benefits, on database queries or something like this.
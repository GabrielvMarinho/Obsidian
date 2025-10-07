A [[Python]] object that can be iterated, implements [[__iter__]]

Example of iterator:
```python
data = "word"
it = iter(data)

print(it)
print(next(it))
print(next(it))
print(next(it))
print(next(it))
```

Output:
```cmd
<str_ascii_iterator object at 0x0000021B401BAEF0>
w
o
r
d
```


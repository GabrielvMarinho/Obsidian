the venv module in [[Python]] is used to handle depencies across different projects.

to create a venv:
```python
python -m venv .venv
```


Structure: 
### Scripts

`python.exe`: an executable that will point to the python interpreter that created the venv (will point to the venv's dependencies instead)
`activate`: script to activate the venv
### Lib

`site-packages`: to store all the dependencies related to that venv

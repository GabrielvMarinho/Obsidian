[[Python]] [[Lib]] for packaging and bundling python apps

## How it works

Pyinstaller ""copies"" the interpreter in the machine building the app, so if the machine building uses python 3.13 the interpreter implemented will be this one

so python is not installed globally but if someone installs the exe it will have access to a python interpreter internally and that pytho interpreter can run outside modules (any .py file)
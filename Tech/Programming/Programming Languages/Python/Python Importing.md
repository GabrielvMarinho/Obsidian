Python always resolves imports relative to the top-level script that was executed, main,  not based on where the file doing the import is

if you are doing a sub application to be called by a higher module, you cant just write:

```python
from file_in_same_folder_as_me import foo 
```

because if its inside a folder and a main file calls for it:

```python
from subapp import main
```

and main has that import it would go wrong, you should rather do this:

```python
from .file_in_same_folder_as_me import foo 
```
to always import relative to this folder
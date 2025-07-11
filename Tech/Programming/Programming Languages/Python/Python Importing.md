Python always resolves imports relative to the top-level script that was executed, __main__ not based on where the file doing the import is

if you are doing a sub application to bbe called by a higher module, you cant just write:

```
from file_in_same_folder_as_me import foo 
```

because if its inside a folder and a main file calls for it:

```
from subapp import main
```
and main has that import it would go wrong, you should rather do this:

```
from .file_in_same_folder_as_me import foo 
```
to always import relative to this folder
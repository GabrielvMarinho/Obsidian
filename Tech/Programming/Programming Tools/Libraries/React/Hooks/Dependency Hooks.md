[[React]] hooks that execute a function whenever a dependency changes, like [[UseEffect]].

Dependency hooks check differently for the changing in dependencies, 
if its a primitive type if will check for the value, if its a complex structure it will look for the reference, not the actual content
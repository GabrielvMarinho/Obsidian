[[Spring]] attribute of [[@NtoN]] that dictates the cascatable operations that are propagated to the assocaiated [[@Entity]]


```java
@OneToMany(mappedBy = "example", cascade = CascadeType.CONSTANT")
```

Here are the [[Constants]] that can be used

1. **NONE** = Does nothing
2. **MERGE** = Updates children when updates the father (only updates)
3. **PERSIST** = Inserts the children when inserts the father
4. **REFRESH** = Updates the father and keeps the children without altering
5. **REMOVE** = Removes the father when removes the children
6. **ALL** = Executes all the operations


source code level coupling

## Types

1. connascence of name -> multiple components agree on the name of an entity
2. connascense of type -> multiple components must agree on the type of an entity
3. connascense of meaning -> multiple components must agree on the meaning of particular values, like constants
4. connascence of position -> multiple entities must agree on the order of values, like the sequence of params in a function
5. connascence of algorithm -> multiple components must agree on a particular algorithm, assume you have algorithms in both client and server, if the server changes the hashing algorith, client would have too, this is connascence of algorithm

[[Connascence]]
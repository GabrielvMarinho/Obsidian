from best to worst:

1. Functional:
every part of the module is related to the other, and the module contains everything essential to function
2. Sequential cohesion:
two modules interact, where one outputs data that becomes the input to the other
3. Communicational cohesion:
two modules form a communication chain where each contributes to generate an output or operate on information, example: add a record to the database and generate an email based on that information.
4. Procedural cohesion:
two modules must execute code in a particular order
5. Temporal cohesion:
modules are related based on timing dependencies
6. Logical cohesion:
the data within modules is realted logically but not functionally, example, a function that converts info to text, serialize objects or streams, operations are related but the functions ar quite different
7. Coincidental cohesion:
elements in a module are not related other than being on the same source file, you never want that
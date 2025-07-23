Depending on the [[Programming Language]] you can have different approaches for building software to be used by another machine, some translate the existing code into machine code and its interpreted by the [[Operating System]], others just bundle an interpreter.


## Who does each?

it really depends on how [[Compilation and Execution of Software]] of given language works, as they are often very related

Low level -> rust, c, go: compile to machine code
High level -> python, javascript: generally use interpreters or [[Tech/Software/Software LifeCycle/Building/JIT]] compilation
languages for portability -> java, c#: generallyt comple to intermediate bytecode run by runtime

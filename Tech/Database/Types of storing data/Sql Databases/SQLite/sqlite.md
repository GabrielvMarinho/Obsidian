A low complexity [[Embedded Database]] that stores all it's data in a single [[DB file]] and doest require a server to be used



## Architecture

because sqlite structure is file based, only one concurrent write at a time can write in it, by default, sqlite cheks the thread in the process to see if its the same one that created the connection in order to permit writing, that can be bypassed but follows with the risk of concurrency erros
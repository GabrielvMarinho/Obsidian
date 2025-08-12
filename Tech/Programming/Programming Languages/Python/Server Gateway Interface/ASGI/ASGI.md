Asynchronous Server Gateway Interface.


So its not the web server itself, its simply a bridge between the app and the actual [[Web Server]]

A set of specifications to describe how web servers should communicate in web [[Asynchronous]] [[Python]] apps.

## Request processing

ASGI processes requests in an asynchronous approach, meaning it can switch between requests within a [[Worker]], to not losing time in I/O tasks, like waiting for a database call, this whole process is named an [[Event loop]].

When many requests are made, It will enter the worker event loop. If a worker has too much load, depending on the config a new worker can be called (new threads can be created but It is not common).
Asynchronous Server Gateway Interface.

A set of specifications on how a web server communicate with asynchronous web applications written in python

An interface that when implemented works as a middleware to connect a web server request to the actual code.

A set of specifications to describe how web servers should communicate in web [[Asynchronous]] [[Python]] apps.
## Request processing

ASGI processes requests in an asynchronous approach, meaning it can switch between requests within a [[Tech/WWW/Web/Web Server/Worker]], to not losing time in I/O tasks, like waiting for a database call, this whole process is named an [[Event Loop]].

When many requests arrive, each worker event loop schedules them. the number of process is fixed at startup.
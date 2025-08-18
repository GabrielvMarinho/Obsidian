Asynchronous Server Gateway Interface.


So its not the web server itself, its simply a bridge between the app and the actual [[Web Server]]

A set of specifications to describe how web servers should communicate in web [[Asynchronous]] [[Python]] apps.

## Request processing

ASGI processes requests in an asynchronous approach, meaning it can switch between requests within a [[Tech/WWW/Web/Web Server/Worker]], to not losing time in I/O tasks, like waiting for a database call, this whole process is named an [[Event loop]].

When many requests arrive, each worker event loop schedules them. the number of process is fixed at startup.
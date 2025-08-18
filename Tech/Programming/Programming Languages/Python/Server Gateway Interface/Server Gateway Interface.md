An interface that works as a middleware to connect a web server request to the actual code.

It's important to notice that even though you can work with a [[WSGI]] and [[ASGI]] number of workers and so on, generally the scalability issue would be handled by something in the bigger picture like kubernetes.
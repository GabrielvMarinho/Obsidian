Depending on the programming language it can natively or not interact with http requests.

If they interact natively, the [[Web Server]] will communicate with the app easily, but if the language doesnt support http communication, you might need a bridge, like [[WSGI]] for python.

The http server receives a request and talks directly with the process that represents the [[Runtime]] of the app.
## Why they are separate

Why arent apps and http servers a single thing? because this creates a separation of concerns and an abstraction on what actually matters the most, the bussiness logic.

Low level configurationg like rate limiting and load balancing is done in the web server for example
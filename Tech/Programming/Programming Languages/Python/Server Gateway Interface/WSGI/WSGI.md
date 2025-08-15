Web Server Gateway Interface.

A set of specifications to describe how web servers should communicate in web [[Synchronous]] [[Python]] apps.

So its not the web server itself, its simply a bridge between the app and the actual [[Web Server]]

## Request processing

WSGI processes requests in a synchronous approach, meaning it blocks the [[Tech/WWW/Web/Web Server/Worker]] Thread when a request needs to be processed. 

```
Webserver thread                      YourCode 
    |                                    |
    |       --callout to WSGI code-->    |
    |                                    |
    |                              [Do stuff ...]
[blocking]                         [     ...    ]
    |                              [Do stuff ...]
    |                                    |
    |                                  Done!
    |   <--Your response to the server-- |
 Proceed!```
```


When many requests are made, since a single one of them blocks the process, a prexistant process is allocated the request. The number of workers is pre setted.
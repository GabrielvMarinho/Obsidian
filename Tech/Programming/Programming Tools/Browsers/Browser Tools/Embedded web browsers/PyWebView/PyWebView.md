[[Embedded web browser]] for python development

Pywebview can generate a web-desktop interface that referentiate to a web server, like a flask server

Pywebview can start serverless applications, just need to send a js_api object with the methods and by calling window.pywebview.api, you will access the object sent, its somewhat of an abstraction, because the object is not actually serializedm (it just is serialized in multiprocess) to be called by javascript, rather proxying calls from js to python in run time. What [[Proxy|proxying]] means? basically creating a bridge or middleman that sends the function name and args, python receives the message and run the method. its essentially calling a pointer to the object
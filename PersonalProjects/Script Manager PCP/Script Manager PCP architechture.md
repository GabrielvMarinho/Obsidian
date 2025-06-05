The project consists of:

1. frontend: react app
2. backend: python
3. wrapper: pywebview


the python backend uses no framework, its a class api used to set methods related to api functions,

the backend interacts with a modelo_default package with different macros in it, each macro being a main.py file with a json to read details about it

the class also has attributes related to websocket communication and so on

this class is instantiate and sent to the front end via pywebview

the react frontend receives a js_api object to access the methods and do so accordingly

the frontend needs to be build each time so that the main "index.html" file can be passed as a parameter to pywebview
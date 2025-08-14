[[NodeJS]] class to handle context at a task.

use case: multiple threads that need an up to date variable across multiple methods without having to pass a ton of params.

Example
```node
import http from "http"
import { AsyncLocalStorage } from "async_hooks"

const als = new AsyncLocalStorage();

http.createServer((req, res) =>{
  als.run(req.url, ()=>{
    console.log(als.getStore())
    service()
  })
}).listen("1234")

function service(){
  //aware of the url even though no params
  console.log(als.getStore())
  database()
}
function database(){
  //aware of the url even though no params
  console.log(als.getStore())
}
```

This is the equivalent of passing req.url in every function, without having to do so.
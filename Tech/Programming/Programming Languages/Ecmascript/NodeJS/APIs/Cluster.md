a cluster of [[NodeJS]] processes can be used to run multiple intances of nodejs (so called workers) to distribute workloads among their application threads.

#### Example:
```node
import cluster from 'node:cluster'

console.log("test")

if (cluster.isPrimary){
  cluster.fork()
  cluster.fork()
}
```
*is primary is stopping it from starting infinite workers*

#### Another example 
```node 
import cluster from 'node:cluster'
import { availableParallelism  } from 'node:os'
import process from 'node:process'
import http from "node:http"
const NUM_OPTIMAL_CPU = availableParallelism()

console.log(`Process ${process.pid}`)
if(cluster.isPrimary){
  for(let i=0; i<NUM_OPTIMAL_CPU; i++){
    cluster.fork()
  }
}
else{
  http.createServer((req, res)=>{
    res.end(`this is a response from worker ${process.pid}`)
  }).listen(8000)
}
```
This example uses multiple workers to respond to a server, however this works poorly if on windows.
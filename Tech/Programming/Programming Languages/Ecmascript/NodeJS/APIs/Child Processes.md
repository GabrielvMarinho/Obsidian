in [[NodeJS]], you have APIs to spawn child processes
### Example

```node
import { exec, spawn } from 'node:child_process';

const dirs = spawn('cmd', ["/c", "dir"]);

dirs.stdout.on("data", (data) =>{
  console.log(`${data}`)
})

//bat has the dir command
exec("my.bat", (err, stdout, stderr) =>{
  console.log(stdout)
})
```

this will print the directories of the new process.
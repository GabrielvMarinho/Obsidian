A Region of memory to store data temporarily while Its being moved or waiting to be used.

A buffer is an abstraction of important methods to handling large data, 

a Region of memory to store data temporarily until its processed.


It's faster to store everything in a buffer and write it to disk once than write in disk each time, this applies to most I/O tasks

An example of what a buffer would look like:
```node
import fs from 'fs';
// --------- NON-BUFFERED APPROACH ---------
console.time("non-buffered");

for (let i = 0; i < 1000; i++) {
  fs.writeFileSync("nonbuffered.txt", "Hello World\n", { flag: 'a' });
}

console.timeEnd("non-buffered");

// --------- BUFFERED APPROACH ---------
console.time("buffered");

let buffer = "";
for (let i = 0; i < 1000; i++) {
  buffer += "Hello World\n";
}

fs.writeFileSync("buffered.txt", buffer);

console.timeEnd("buffered");


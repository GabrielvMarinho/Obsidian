[[NodeJS]] is by default single threaded, however, many native APIs it uses are executed in different [[thread]]s ([[Libuv]] thread pool).

An overview of how that works:
```node
const fs = require('fs');

console.log("Start reading file...");

// Asynchronous file read (runs in a libuv thread)
fs.readFile('example.txt', 'utf8', (err, data) => {
  if (err) {
    console.error("Error reading file:", err);
    return;
  }
  console.log("File contents:", data);
});

console.log("This runs while the file is being read...");

```

fs readFile is an API, when you call it, it runs in a different thread.

The callback function will be invoked back into the [[Event Loop]] call stack after the new thread finished the I/O (once the call stack is free of running tasks).


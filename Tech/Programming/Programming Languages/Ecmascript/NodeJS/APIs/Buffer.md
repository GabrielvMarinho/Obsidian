first check what a [[Tech/Software/Arquitecture/Memory/Buffer/Buffer|Buffer]] is.

[[NodeJS]] offers a built in buffer API for abstracting some functionalities from the Uint8array.

Class extends the Uint8array which has some features to handle data, the flow looks like this:

### Flow

1. String input to Buffer ("hello")
     
2. Encode string into bytes using UTF-8 or another char encoding standard (``[104, 101, 108, 108, 111]``)
    
3. sends the char array to instantiate a Uint8array Object

### Example of use

```node
// buffer_cheatsheet.js

// --- Creation ---
const buf1 = Buffer.from("Hello", "utf8");   // from string
const buf2 = Buffer.alloc(5);                // zero-filled
const buf3 = Buffer.allocUnsafe(5);          // uninitialized
console.log(buf1, buf2, buf3);

// --- Conversion ---
console.log(buf1.toString("utf8")); // -> Hello
console.log(buf1.toString("hex"));  // -> 48656c6c6f

// --- Read & Write ---
buf2.write("Hi"); 
console.log(buf2.toString()); // -> Hi

// --- Fill & Copy ---
buf2.fill(65); // 'A'
console.log(buf2.toString()); // -> AAAAA
buf1.copy(buf2);
console.log(buf2.toString()); // -> Hello

// --- Slice (shared memory) ---
const part = buf1.slice(0, 2);
console.log(part.toString()); // -> He

// --- Utilities ---
console.log(Buffer.byteLength("Hello"));  // -> 5
console.log(Buffer.isBuffer(buf1));       // -> true
console.log(Buffer.concat([buf1, Buffer.from(" World")]).toString());

```
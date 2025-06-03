allows [[Tauri Webview]] interface to interact with the [[Rust]] backend.

it exposes all modules as an object where the key is the object name and the value is the module exports.


makes it easy to access backend methods and modules though js for example:

```js
import { invoke } from '@tauri-apps/api/tauri'
```

though this method can invoke the rust backend
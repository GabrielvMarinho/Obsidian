[[Hooks (React)|Hook]] in [[React]] to let you store a variable in a component

```jsx
const [state, setState] = useState(initialState)
```

```jsx
import React, { useState } from 'react';

function CounterApp() {
    // Declare a state variable `count` with an initial value of 0
    const [count, setCount] = useState(0);

    return (
        <div>
            <h1>Counter: {count}</h1>
            <button onClick={() => setCount(count + 1)}>Increment</button>
            <button onClick={() => setCount(count - 1)}>Decrement</button>
        </div>
    );
}

export default CounterApp;
```
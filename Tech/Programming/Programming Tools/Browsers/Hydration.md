the process on which [[Javascript]] on the client side process a static webpage and turn into a dynamic web page by adding event handlers on the [[DOM]].

## Example

This will throw an error:
```jsx
"use client"

export default function Home() {

    const date = new Date()
    console.log()
    return (
        <div>{date.getMilliseconds()}</div>

    );

}
```
Because the server side render was different from the client side render.

Even though it has a "use client" the parent was server side, so it actually tried to prerender the component anyway.
1. Browser sends request to server.
2. Gets some data and injects into components (like React ones).
3. Framework (like react) executes the components on the server, producing static html with dynamic data for initial page load.
4. Server sends the rendered HTML.
5. [[Hydration]] happens, where the event handlers are added, making the page "partially rerender"

### Cookies

Local storage is very limited when it commes to working with ssr, [[Cookies|Cookies]] are the way to go
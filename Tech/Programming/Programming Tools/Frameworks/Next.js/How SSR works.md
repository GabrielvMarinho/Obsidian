It renders all the content of the page in the server, but what does that actually mean, doesnt all the pages already return the html from the server? yes, but without ssr it would just return a bunch of code to be ran on the [Browser](obsidian://open?vault=Obsidian&file=Tech%2FSoftware%2FConcepts%2FMISCELLANEOUS%2FBrowser) while in ssr it will be ran on the server, that can be seen in script tags, for example, which just sends the function, not the actual data. Notice that just the HTML will be loaded in the server, no script functionality.

Thats why in the final project I lost so much time not understading why my credentials include werent sending shit, it was because it was looking for the cookies in the browser but the fetch was a server component, now i have 50+ fetches and each one of them is either client or server child, and there is no way to tell, I will have to check one by one and if used in both situations I will have to create two because the fuckers in the server cant just use credentials include, and actually have to look up the httponly cookies in the request made to the server.


### Cookies

Local storage is very limited when it commes to working with ssr, [[Cookies|Cookies]] are the way to go
I tried implementing a localstorage theme manager in next js, the problem was, i had to point that something in my html changed for my css to swap the variables, the css was looking for the attribute data-theme of the main html tag.

The problem with this is, data-theme wasnt set, the only way to set it was to render in the client browser because that where the local storage is, so i just couldnt do it.

the solution was simple, using cookies, cookies are goated because i manage to render the theme in the server, since the cookies are sent in the headers, then, i could access the theme in both client and server, no worries, to manage the change of state was just as easy, if not easier than with localStorage
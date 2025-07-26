Cross Site Request Forgery.

Its an attack that happens when a malicious application tries to use your browser saved session to execute actions in a application you have access to, like a website trying to use javascript tags to make you do a request with your local storage javascript available token.

You can solve that by using httponly cookies, same site cookies or [[CSRF Tokens]].
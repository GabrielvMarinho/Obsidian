an open source tool for [[Web Authentication]]

It uses [[Asymmetric (RS256)]] signing of [[JWT|JWTs]] the flow usually goes like this

1. User logins in frontend
    
2. Keycloak receives user info like password and username
    
3. Keycloak retrives a jwt and a refresh token (usually easier to deal with ssr frameworks)
    
4. Frontend tries to go for an api call
    
5. The api will use keycloaks public key to validate the jwt

## More details

3. the refresh token is used to get new jwts, they are created new ones because it always create a different jwt to not expose a key for too long

## What it abstracts

Keycloak abstract a lot of processes of authentication, like users login, signin, forgotten password, etc. 
Making the main use of it an out of the box implementation of those services aswell as more security preventions. Even though robust, keycloak just actually makes sense when the auth system needs to be descentralized, mostly because an app could be divided into sub apps. Keycloak makes it unnecessary to impl auth in each subapp.
#### One login

The request in a login page redirects you to a keycloak server, if you use another sub app login page, it will set as logged in because [[Cookies]] are saved by url, and that keycloak server already has a token.


an open source tool for [[Web Authentication]]

It uses [[Asymmetric (RS256)]] signing of [[JWT|JWTs]] the flow usually goes like this

1. User logins in frontend
    
2. Keycloak receives user info like password and username
    
3. Keycloak retrives a jwt
    
4. Frontend tries to go for an api call
    
5. The api will use keycloaks public key to validate the jwt
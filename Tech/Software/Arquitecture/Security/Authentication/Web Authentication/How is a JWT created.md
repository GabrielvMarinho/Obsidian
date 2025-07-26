A [[JWT]] (JSON Web Token) is generated using a combination of a **cryptographic algorithm** (such as `HS256` or `RS256`) and a **secret key** (or a private key, depending on the algorithm)

The **signature** of the JWT is created by taking the encoded header and payload, joining them with a dot (`.`), and then signing that string using the chosen algorithm and secret.

This signature ensures the integrity of the token — if someone tries to modify the payload or header, the signature will no longer match when verified. Therefore, only someone with the correct secret key can generate a valid signature.
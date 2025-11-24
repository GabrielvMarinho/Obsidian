The private key signs it, the public key verifies it.

An issuer with a private key will create a token, your api will then query for a public key of the issuer, this public key is enough to validate, but not enough to create new tokens, that, only the issuer can do.

The private key in the issuer signs it, the public key in the api, queried of the issuer, validates it.

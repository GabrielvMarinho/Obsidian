The secret key both sign and verify the key.

you have a content, like user info, you then will use symmetric signing to create a signature, if someone tries to change user info, like the role, the server will notice something is up and will not validate.

The process of creating the signature and validating is both done by the same secret key.
A [[Spring]] [Lib](obsidian://open?vault=Obsidian&file=Tech%2FSoftware%2FConcepts%2FMISCELLANEOUS%2FLib) for managing users and roles


### Spring Security Code Example

1. [[Injecting Dependencies Simple Auth Logic Process Spring Security|Injecting Depedencies]]
2. [[Create UserRepository Simple Auth Logic Process Spring Security|User Repository UserDetailsService]]
3. [[Create Implementation Of UserDetailsService Simple Auth Logic Process Spring Security|Implementation UserDetailsService]]
4. [[Create Beans Simple Auth Logic Spring Security|Creating Beans]]
5. [[Receive Credentials with DTO Simple Auth Logic Spring Security|Receiving Credentials]]
6. [[Create An Object Implementing Authentication Simple Auth Logic Spring Security|Create Authentication Object]]
7. [[Authenticate Object Simple Implementing Authentication Auth Logic Spring Security|Authenticate Object]]
8. [[Check The Object Implementing Authentication Simple Auth Logic Spring Security|Check The Object]]
9. [[Create Context If Authenticated Simple Auth Logic Spring Security|Create Context]]
10. [[Save Context Simple Auth Logic Spring Security|Save Context]]
11. [[Checking Context Simple Auth Logic Spring Security|Check Context]]
### Spring Security Flow

![[Spring Security Flow.png]]

# The flow

1. The credentials are sent from the front end to the authentication filter

2. Intecerpts every single request to allow or to deny access

3. The authentication manager is responsible for seeing which authentication provider will be used

4. Once the authentication provider is chosen (google auth or your own database with username and password)

5. The authentication provider first checks the user details service to see if the user exists (by username)

6. If it exists he will get the plain text password, encrypt and compare with the crypted password, once all these are confirmed and validated, the security context will be saved, when saving the context in the server or using JWT this process still happens, even if using jwts the context is set and saved momentarily to let the user use the endpoint,

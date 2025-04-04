A [[Spring]] [Lib](obsidian://open?vault=Obsidian&file=Tech%2FSoftware%2FConcepts%2FMISCELLANEOUS%2FLib) for managing users and roles


### Spring Security Example

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

Security Context: Saves the context so the user can log once and save for a while
Authentication Manager: Gerencia e decide o Provider para verificar o usuário (google, banco de dados local, etc.)
Authentication Provider: Procura o usuário pelo username usando o user details service e depois verificar a senha no password encode, responsável por acionar cada um dos blocos. O google por exemplo é um provider, ou podemos criar para buscar no nosso banco



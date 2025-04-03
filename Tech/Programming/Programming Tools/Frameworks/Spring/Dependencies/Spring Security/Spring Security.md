A [[Spring]] [Lib](obsidian://open?vault=Obsidian&file=Tech%2FSoftware%2FConcepts%2FMISCELLANEOUS%2FLib) for managing users and roles


### Spring Security Example

[[Injecting Dependencies Simple Auth Logic Process Spring Security|Injecting Depedencies]]
[[Create Beans Simple Auth Logic Spring Security|Creating Beans]]
[[Receive Credentials with DTO Simple Auth Logic Spring Security|Receiving Credentials]]
[[Create An Object Implementing Authentication Simple Auth Logic Spring Security|Create Authentication Object]]
[[Authenticate Object Simple Implementing Authentication Auth Logic Spring Security|Authenticate Object]]
[[Check The Object Implementing Authentication Simple Auth Logic Spring Security|Check The Object]]
[[Create Context If Authenticated Simple Auth Logic Spring Security|Create Context]]
[[Save Context Simple Auth Logic Spring Security|Save Context]]
[[Checking Context Simple Auth Logic Spring Security|Check Context]]
### Spring Security Flow

![[Spring Security Flow.png]]

Security Context: Saves the context so the user can log once and save for a while
Authentication Manager: Gerencia e decide o Provider para verificar o usuário (google, banco de dados local, etc.)
Authentication Provider: Procura o usuário pelo username usando o user details service e depois verificar a senha no password encode, responsável por acionar cada um dos blocos. O google por exemplo é um provider, ou podemos criar para buscar no nosso banco



How layered architecture is divided generally:

Model - Service, repository, model (Backend)
Controller -  Intermediador Back e Front
View - (Frontend)

## Models

Represents the [Data](obsidian://open?vault=Obsidian&file=Tech%2FDatabase%2FData) structure and entities of an application  

example: 

```
class User {
    id: Integer
    name: String
    email: String
    password: String  // Sensitive data not included in DTO
    created_at: DateTime
}

```
## DTOs (Data transfer [Object](obsidian://open?vault=Obsidian&file=Tech%2FProgramming%2FProgramming%20Paradigms%2FOOP%2FConcepts%2FObject)s)

simplify the transfer of [Data](obsidian://open?vault=Obsidian&file=Tech%2FDatabase%2FData) between layers, so like between services and controller

Example:

```
class UserDTO {
    id: Integer
    name: String
    email: String
}
```
## Controllers

Just the middleman
Handle [HTTP](obsidian://open?vault=Obsidian&file=Tech%2FNetwork%2FPROTOCOLS%2FHTTP%2FHTTP) requests processing them through services and send responses

Example:

```
ControllerFunction() {
	services.function()
	return true
}
```
## Services 

Contains the business logic and common validations, they bascially do the non-generic work, that is up to the business owner to decide (or the dev he hires)

Example: 

```
ServiceFunction(object){
	if(object == "validated"){
		return true
	}
	return false
}
```
## Repositories

Handle the interaction with the [DataBase](obsidian://open?vault=Obsidian&file=Tech%2FDatabase%2FDataBase) like [Sql](obsidian://open?vault=Obsidian&file=Tech%2FDatabase%2FSql%20Databases%2FSql) commands

Example:

```
InsertInto(id, nome){
	Execute.Query("INSERT INTO xtable (id, name) VALUES ( {id}, {nome})")
}
```

this function is later on called by the services generally
## Routes

Define the mapping between [HTTP](obsidian://open?vault=Obsidian&file=Tech%2FNetwork%2FPROTOCOLS%2FHTTP%2FHTTP) URLs and the controller methods to handle them

Example:

```
@("/something) -> ControllerFunction()
```
When It comes to code structure, following a pattern and having an organized approach can really make the project 1000x easier in the long run

## A Generic approach

In a generic approach where we need a simple app with a [[BackEnd]], [[FrontEnd]] and a [[DataBase]], we can separete into 6 archives

### 1. Models

Entities related to the database
### 2. DTO

A momentary entities to control whats the users receives
### 3. Controller

[[HTTP]] methods such as [[GET]] and [[POST]]
### 4. Routes

Basically the [[URL]]
### 5. Services

The business rules and requirements
### 6. Repositories

The data base queries/commands
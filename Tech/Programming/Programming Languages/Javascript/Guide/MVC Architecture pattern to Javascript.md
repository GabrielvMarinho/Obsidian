Let's see how to do a [Layered Architecture (MVC)](obsidian://open?vault=Obsidian&file=Tech%2FSoftware%2FSoftware%20Arquitecture%2FPatterns%20of%20software%2FLayered%20Architecture%2FLayered%20Architecture%20(MVC)) pattern code in [[Javascript]]

ta certo a importação do connection ta certo ser no repository?
o controller é responsavel pelo res ou poderia ser na ultima camada (repository)?

The flow of the application is basically:
1. the app is started in app.js 
2. app.js requires the routes;
3. the routes dictates which [URL](obsidian://open?vault=Obsidian&file=zzzzzzzzzzz%2FURL) is for each controller
4. the controller requests a serie of DTOs from the service layer
5. the service layer sends a [Sql](obsidian://open?vault=Obsidian&file=Tech%2FDatabase%2FSql%20Databases%2FSql) command to repository
6. the repository executes the [Sql](obsidian://open?vault=Obsidian&file=Tech%2FDatabase%2FSql%20Databases%2FSql) command
7. based on the response from the database, he turns it into a model
8. the model is sent to services 
9. the model is turned into a [[DTO]] in the service layers
10. the DTO is sent to the controller layer
11. the DTO is turned into plain text (maybe should have been done in the service layer)
12. the text is sent to the person who requested the [API](obsidian://open?vault=Obsidian&file=Tech%2FSoftware%2FConcepts%2FBACK-END%2FAPI%2FAPI)

good to pay attention to the fact that every thing related to the business logic is in the service layer, so the value of the [Sql](obsidian://open?vault=Obsidian&file=Tech%2FDatabase%2FSql%20Databases%2FSql) command is defined in the service layer, aswell as how the DTO is going to be turned into a model.
## /CONTROLLERS
#### userController.js

```js
const selectService = require("../SERVICES/userService.js")


async function selectController(req, res){
    try{
        const userSTOs = await selectService()
        var texto = ""
        for(var i=0;  i<userSTOs.length; i++){
            texto += "| id: "+userSTOs[i].id + " - nome: "+ userSTOs[i].nome
        }
        res.status(200).json(texto)
    }catch(error){
        res.status(500).json("Erro ao fazer operação crud")
    }
}
module.exports = selectController
```
## /DTOS
#### userDTOs
```js
class UserDTO{
    constructor(id, nome){
        this.id = id;
        this.nome = nome;
    }
}  

module.exports = UserDTO
```
## /MODELS
#### userModel.js
```js
class UserModel{
    constructor(id, nome, data_criacao){
        this.id = id;
        this.nome = nome;
        this.data_criacao = data_criacao
    }
}  
module.exports = UserModel
```
## /REPOSITORIES
#### userRepository
```js
const userModel = require("../MODEL/userModel")
const con = require("../SERVICES/dbCon.js")

async function selectRepository(sql){

    return new Promise(resolve =>{
        con.query(sql, function (err, result) {
            var array =[]
            console.log(result.length)
            for(var i=0; i<result.length; i++){
                var user = new userModel(result[i].id, result[i].nome, result[i].data_criacao)
                array.push(user)
            }
            resolve(array)
        })
    })
}
module.exports = selectRepository;
```
## /ROUTES
#### userRoutes.js
```js
const express = require("express");
const selectController = require("../CONTROLLER/userController.js")

const router =express.Router()
router.get("/select", selectController)

module.exports = router
```
## /SERVICES
#### dbCon.js
```js
var mysql = require("mysql")

const con = mysql.createConnection({
    host: "localhost",
    user: "root",
    password: "",
    database: "banco"
})

con.connect(function(err){
    if(err){
        console.log("ERRO NO DB")
        return;
    }
    console.log("Conectado")
})

module.exports = con
```

#### userService.js
```js
const selectRepository = require("../REPOSITORY/userRepository")
const userDTO = require("../DTOs/userDTOs")

async function selectService(con){
    //the sql command and the dto are defined here because they correlate to the business logic
    var sql = `SELECT * FROM usuario`;
    const users = await selectRepository(sql)
    var usersDTOs = [];
    
    for(var i=0; i<users.length; i++){
        var userdto = new userDTO(users[i].id, users[i].nome)
        usersDTOs.push(userdto)
    }
    console.log(usersDTOs)
    return usersDTOs
}

module.exports = selectService;
```
## app.js
```js
const express = require("express");

//starting the app
const app = express()
//instructing the app to listen to this port
app.listen(3000)
app.use(express.json())

const router = require("../APP/ROUTES/userRoutes")

app.use("/", router)
```
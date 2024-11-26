Creating an [[API]] from scratch using [[Javascript]] and [[Express]]

Commands:

1. 
```
npm init -y
```
2.  
```
npm install express axios
```

## The code itself:

```js
//importa as dependências
const express = require('express');
const axios = require('axios');
  

const app = express();

//for reading json in body
app.use(express.json());

const PORT = 3000

app.listen(PORT)

app.get('/pessoa', async(req, res) =>{
    try{
        res.status(200).json({message: "Mensagem de sucesso"})
    }catch(error){

        res.status(500).json({error: "Mensagem de erro"})
    }
});
```

to run:

To test just access http://127.0.0.1:3000/pessoa in your [[Browser]] or use [[PostMan]] (better)


## More Examples with parameters [[GET]] and [[POST]]:

```js
app.get('/atividade1/:id/:nome/:idade', async(req, res) =>{
    try{
        let id = req.params.id
        let nome = req.params.nome
        let idade = req.params.idade
        res.status(200).json({message: `Olá ${nome} você tem ${idade} anos e seu id é ${id}`})  
    }catch(error){
        res.status(500).json({error: "Mensagem de erro"})
    }
});

app.get('/atividade2/:cpf/:nome', async(req, res)=>{
    try{
        let cpf = req.params.cpf
        let nome = req.params.nome
        res.status(200).json({message: `Olá ${nome}, não irei falar seu cpf pois é segredo`})
    }catch(error){
        res.status(500).json({error: "Mensagem de erro"})
    }
})


app.use(express.json());
app.post("/atividade3", async(req, res)=>{
    try{
        const corpoDaRequisicao = req.body;
        res.status(201).send(corpoDaRequisicao)
    }catch(error){
        res.status(500).json({error: "Mensagem de erro"})
    }
})
```

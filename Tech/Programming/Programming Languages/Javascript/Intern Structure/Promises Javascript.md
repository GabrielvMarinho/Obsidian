Promise is an [[Object]] in [[Javascript]] that represents a pending task


Pending → Fulfilled (success) 
Pending → Rejected (an error occurred)

Creating a promise
```js
function downloadSimu(){
    return new Promise((resolve, reject) => {
        if(0.5 > Math.random()){
            resolve("Dados carregados")
        }
        else{
            reject("Dados não carregados")
        }
    })
}
downloadSimu().then((resultado =>{
    console.log(resultado)
})).catch((erro) =>{
    console.log(erro)
})
```

Can be used in an e-commerce to validate some order for example


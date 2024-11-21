local storage in [[Javascript]] can really help you save important info about a user, it can save data without exactly using a [[DataBase]]

It works with a key value format, like a [[JSON]] file
## Commands

settting a value:
```javascript
localStorage.setItem("nome", "João");
```

getting a value:
```javascript
const nome = localStorage.getItem("nome"); 
console.log(nome); // Saída: João
```

getting a key:
```javascript 
console.log(localStorage.key(0)); // Saída: nome 
```

removing a values:
```javascript
localStorage.removeItem("idade");
```

remove all values:
```javascript
localStorage.clear();
```

storing objects:
```javascript
const usuario = { nome: "João", idade: 30, cidade: "São Paulo", }; // Convertendo para string JSON e armazenando 

localStorage.setItem("usuario", JSON.stringify(usuario)); // Recuperando e convertendo de volta para objeto 

const dadosUsuario = JSON.parse(localStorage.getItem("usuario")); console.log(dadosUsuario.nome); // Saída: João
```


local storage in [Javascript](obsidian://open?vault=Obsidian&file=Tech%2FProgramming%2FProgramming%20Languages%2FJavascript%2FJavascript) can really help you save important info about a user, it can save [Data](obsidian://open?vault=Obsidian&file=Tech%2FDatabase%2FData) in a [[Browser]] without exactly using a [DataBase](obsidian://open?vault=Obsidian&file=Tech%2FDatabase%2FDataBase)

It works with a key value format, like a [JSON](obsidian://open?vault=Obsidian&file=Tech%2FDatabase%2FJSON) file
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


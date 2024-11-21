the [[Callback]] in [[Javascript]] can be written this way:


```js
function saudacao(nome, callback) { 
	console.log(`Olá, ${nome}`); 
	callback(); 
} 

function mensagemFinal() { 
	console.log("Volte Sempre!"); 
} 

function mensagemInicial() { 
	console.log("Bem-vindo ao nosso sistema!"); 
} 

saudacao("Maria", mensagemInicial); 
saudacao("Maria", mensagemFinal);


//Output

```
Output:
```
Olá, Maria 
Bem-vindo ao nosso sistema! 
Olá, Maria 
Volte Sempre!
```

Now callbacks with [[Asynchronous]] [[Function]]s:

```js
console.log("Início"); 
setTimeout(() => { 
	console.log("Executando callback após 2 segundos"); 
}, 2000); 
console.log("Fim");
```
Output:
```
Início 
Fim 
Executando callback após 2 segundos
```
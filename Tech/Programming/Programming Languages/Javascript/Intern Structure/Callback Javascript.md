the [Callback](obsidian://open?vault=Obsidian&file=Tech%2FProgramming%2FProgramming%20Tools%2FCallback) in [[Javascript]] can be written this way:


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

Now callbacks with [Asynchronous](obsidian://open?vault=Obsidian&file=Tech%2FSoftware%2FConcepts%2FMISCELLANEOUS%2FAsynchronous) [Functions](obsidian://open?vault=Obsidian&file=Tech%2FProgramming%2FProgramming%20Tools%2FFunction):

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
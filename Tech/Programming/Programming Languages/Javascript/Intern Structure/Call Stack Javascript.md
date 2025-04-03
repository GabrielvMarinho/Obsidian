Its a [[Stack]] is a structure responsible for organizing the functions in [[Javascript]]

when called, the [[Function]] is added on top of the stack and only get out when Its execution is finished.

It can be tested by calling functions inside other functions:
```js
function funcA() { 
	console.log("Executando A"); 
} 
function funcB() { 
	console.log("Executando B"); 
	funcA(); 
} 
function funcC() { 
	console.log("Executando C"); 
	funcB(); 
} 
funcC();



```
Output:
```
Executando C 
Executando B 
Executando A
```

The Flow:
- `funcC` is added to the stack.
- Inside `funcC`, `funcB` is called and added to the top.
- Inside `funcB`, `funcA` is called and added to the top.
- `funcA` finishes and is removed.
- `funcB` finishes and is removed.
- `funcC` finishes and is removed.
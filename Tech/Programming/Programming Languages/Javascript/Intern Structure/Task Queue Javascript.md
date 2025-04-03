Its a [Queue](obsidian://open?vault=Obsidian&file=Tech%2FDataScience%2FData%20Structure%2FQueue) where the [Asynchronous](obsidian://open?vault=Obsidian&file=Tech%2FSoftware%2FConcepts%2FMISCELLANEOUS%2FAsynchronous) tasks in [[Javascript]] waits to be executed

It can be tested like this:
```js
console.log("Início"); 
setTimeout(() => { 
	console.log("Tarefa Assíncrona"); 
}, 2000); 
console.log("Fim");
```
Output:
```
Início
Fim 
Tarefa Assíncrona
```

The flow:
- "Start" is displayed in the console.
- `setTimeout` is registered in the Web [API](obsidian://open?vault=Obsidian&file=Tech%2FSoftware%2FConcepts%2FBACK-END%2FAPI%2FAPI) and scheduled to move its callback function to the Task Queue after 2 seconds.
- "End" is displayed in the console.
- When the Call Stack is empty, the `setTimeout` callback is moved from the Task Queue to the Call Stack and executed.
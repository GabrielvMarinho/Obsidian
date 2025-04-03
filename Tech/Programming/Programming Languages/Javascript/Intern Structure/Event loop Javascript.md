Its a mechanism in [[Javascript]] that coordinates the execution of the [[Call Stack Javascript]] and the [[Task Queue Javascript]]

### How the Event Loop Works

1. The Event Loop constantly monitors the Call Stack.
2. When the Call Stack is empty, it checks the Task Queue.
3. Tasks in the Task Queue are moved to the Call Stack and executed.

To test It we can do this:
```js
console.log("Início");

setTimeout(() => { 
	console.log("Tarefa Assíncrona 1"); 
}, 2000); 

setTimeout(() => { 
	console.log("Tarefa Assíncrona 2"); 
}, 1000); 

console.log("Fim");


```
Output:
```
Fim 
Tarefa Assíncrona 2 
Tarefa Assíncrona 1
```

The Flow:
1. "Start" is displayed in the console, and execution continues.
2. The first `setTimeout` is registered in the Web [API](obsidian://open?vault=Obsidian&file=Tech%2FSoftware%2FConcepts%2FBACK-END%2FAPI%2FAPI) and scheduled to move its task to the [[Task Queue Javascript]] in 2 seconds.
3. The second `setTimeout` is registered in the Web API and scheduled to move its task to the Task Queue in 1 second.
4. "End" is displayed in the console.
5. After 1 second, the callback of the second `setTimeout` is moved from the Task Queue to the [[Call Stack Javascript]] and executed.
6. After 2 seconds, the callback of the first `setTimeout` is moved from the Task Queue to the Call Stack and executed.
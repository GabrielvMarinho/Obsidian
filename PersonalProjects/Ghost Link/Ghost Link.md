Hiding a link (just the style, still attracts the target node):

```js
graph.view.renderer.links = []
```

getting the source and forward note:

```js
var graph = this.app.workspace.getLeavesOfType("graph")[0];
var links = graph.view.renderer.links;
//source
console.log(link.source.id)
//forward
console.log(link.target.id)
```


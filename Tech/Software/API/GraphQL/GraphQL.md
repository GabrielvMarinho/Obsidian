Graph Query language

Query data language for [[API]]s

The idea is to expose all the data types and let the client choose for it:
instead of creating an endpoint for foo and bar, you create a Query that the client can specify if they want foo, bar or both:

api.js
```js
type Query{
	foo: Foo
}
type Foo{
	id: String
	bar: Bar 
}
type Bar{
	id: String
}
```

on the client:
```js
{
	foo {
		bar{
			id
		}
	}
}
```

## Trade off analysis

pros:
- adapts to client's need easily
- distributed teams can integrate work seamlessly

cons:
- hard to implement caching
- hard to implement at all
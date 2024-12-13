Its an archtecture for managing non-relational [[Data]] in a giving [[DBMS]]

NoSql stands for Not-only Sql because some nosql [[DataBase]]s actually uses small implementations of [[Sql]] Itself

It uses [[JSON]] files basically and the registers are dynamic, one user can have name and email while one only has name, It's not that the email is null, It simply doesn't exist in that specific table

An example might clarify things:

```
{
	"users": {
	    "1": {
	      "name": "John Doe",
	      "email": "johndoe@example.com",
	    },
	    "2": {
	      "name": "Jane Smith",
	    }
	}
}
```

Only John Doe has the attribute email
How to use format a [[JSON]] in [[Java]]

String to JSON:
```
String json;
JsonObject jsonObject = JsonParser.parseString(json).getAsJsonObject();
```

Manipulating a JsonObject:
```
String email = jsonObject.get("email").toString();
jsonObject.put("name", "John Doe");
```

JsonObject to String:
```
String jsonString = jsonObject.toString();
```



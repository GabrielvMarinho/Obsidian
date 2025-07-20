Chase for explicitness over simplicity, its common to know what a code does, but can be really hard to understand whats It is really doing

simple code
```java
public static boolean function(String value, int value1) {
    if (array.contains(value)) {
        if (value1 >= 7) {
            return false;
        }
        return true;
    }
    return false;
}
```

simple, explicit code
```java
public static boolean isTokenValid(String token, int lifeTimeInDays) {
    if (arrayOfTokens.contains(token)) {
        if (lifeTimeInDays >= 7) {
            return false;
        }
        return true;
    }
    return false;
}
```
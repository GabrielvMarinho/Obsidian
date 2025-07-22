procedural code makes it easy to add new functions without changing the existing data structure. OOP code, on the other hand, makes it easy to add new classes without changing existing functions

procedural code makes it hard to add new data structures because all the functions must change. OOP makes it hard to add new functions because all the classes must change

Procedural: easy to add functions, hard to add new shape(class)
```java
class Square { double side; }
class Triangle { double base, height, a, b, c; }

class Geometry {
    static double area(Object s) {
        if (s instanceof Square sq) return sq.side * sq.side;
        if (s instanceof Triangle t) return 0.5 * t.base * t.height;
        return 0;
    }
}
```

OOP: easy to add new shape(class), hard to add new function
```java
interface Shape {
    double area();
}

class Square implements Shape {
    double side;
    public double area() { return side * side; }
}

class Triangle implements Shape {
    double base, height;
    public double area() { return 0.5 * base * height; }
}

```
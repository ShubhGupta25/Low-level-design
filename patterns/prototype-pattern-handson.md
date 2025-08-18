# Prototype Pattern - Hands-on

## Implementation Example (Java)

```java
class Shape implements Cloneable {
    public Shape clone() throws CloneNotSupportedException {
        return (Shape) super.clone();
    }
}
class Main {
    public static void main(String[] args) throws CloneNotSupportedException {
        Shape shape1 = new Shape();
        Shape shape2 = shape1.clone();
        System.out.println("Shape cloned");
    }
}
```

## How it works

- clone() creates a copy of the object

# Prototype Pattern

## What is it?

A creational design pattern that lets you copy existing objects without making code dependent on their classes.

## When to Use

- Need to create objects based on a template
- Object creation is expensive

## How to Use

1. Implement a clone method in your class
2. Use the clone method to create new objects

## Example (Java)

```java
class Shape implements Cloneable {
    public Shape clone() throws CloneNotSupportedException {
        return (Shape) super.clone();
    }
}
```

## Advantages

- Reduces cost of object creation
- Avoids subclassing

## Disadvantages

- Cloning can be tricky
- May require deep copy logic

# Adapter Pattern

## What is it?

A structural design pattern that allows objects with incompatible interfaces to work together.

## When to Use

- Integrate legacy or third-party code
- Interface mismatch between classes

## How to Use

1. Define target interface
2. Implement adapter class that wraps adaptee and implements target interface

## Example (Java)

```java
interface Target {
    void request();
}
class Adaptee {
    public void specificRequest() { System.out.println("Specific request"); }
}
class Adapter implements Target {
    private Adaptee adaptee;
    public Adapter(Adaptee adaptee) { this.adaptee = adaptee; }
    public void request() { adaptee.specificRequest(); }
}
```

## Advantages

- Reuse existing code
- Decouples client from adaptee
- Flexible integration

## Disadvantages

- Adds extra code and complexity
- May impact performance

# Bridge Pattern

## What is it?

A structural design pattern that separates abstraction from implementation so they can vary independently.

## When to Use

- Decouple abstraction from implementation
- Need to extend both abstraction and implementation independently

## How to Use

1. Define abstraction and implementation interfaces
2. Implement concrete classes for both
3. Abstraction holds a reference to implementation

## Example (Java)

```java
interface Device {
    void turnOn();
}
class TV implements Device {
    public void turnOn() { System.out.println("TV on"); }
}
class Remote {
    private Device device;
    public Remote(Device device) { this.device = device; }
    public void pressButton() { device.turnOn(); }
}
```

## Advantages

- Decouples abstraction and implementation
- Flexible and extensible

## Disadvantages

- More classes
- Increased complexity

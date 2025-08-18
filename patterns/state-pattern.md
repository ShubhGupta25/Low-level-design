# State Pattern

## What is it?

A behavioral design pattern that allows an object to change its behavior when its internal state changes.

## When to Use

- Object behavior depends on its state
- Avoid large conditional statements for state transitions

## How to Use

1. Define a state interface
2. Implement concrete state classes
3. Context class maintains a reference to a state and delegates behavior

## Example (Java)

```java
interface State {
    void handle();
}
class OnState implements State {
    public void handle() { System.out.println("Device is ON"); }
}
class OffState implements State {
    public void handle() { System.out.println("Device is OFF"); }
}
class Device {
    private State state;
    public void setState(State state) { this.state = state; }
    public void request() { state.handle(); }
}
```

## Advantages

- Cleaner code for state-dependent behavior
- Easy to add new states
- Eliminates complex conditionals

## Disadvantages

- Increases number of classes
- Can be overkill for simple state logic

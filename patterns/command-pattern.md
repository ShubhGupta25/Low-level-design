# Command Pattern

## What is it?

A behavioral design pattern that turns a request into a stand-alone object containing all information about the request.

## When to Use

- Parameterize objects with operations
- Support undo/redo
- Queue requests

## How to Use

1. Define a command interface
2. Implement concrete command classes
3. Invoker calls command

## Example (Java)

```java
interface Command {
    void execute();
}
class Light {
    public void on() { System.out.println("Light on"); }
}
class LightOnCommand implements Command {
    private Light light;
    public LightOnCommand(Light light) { this.light = light; }
    public void execute() { light.on(); }
}
class Remote {
    private Command command;
    public void setCommand(Command command) { this.command = command; }
    public void pressButton() { command.execute(); }
}
```

## Advantages

- Decouples sender and receiver
- Supports undo/redo
- Flexible and extensible

## Disadvantages

- More classes
- Can be overkill for simple operations

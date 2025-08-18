# Command Pattern - Hands-on

## Implementation Example (Java)

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
class Main {
    public static void main(String[] args) {
        Light light = new Light();
        Command command = new LightOnCommand(light);
        Remote remote = new Remote();
        remote.setCommand(command);
        remote.pressButton(); // Light on
    }
}
```

## How it works

- Command encapsulates request
- Invoker calls command

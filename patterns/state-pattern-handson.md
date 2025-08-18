# State Pattern - Hands-on

## Implementation Example (Java)

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
class Main {
    public static void main(String[] args) {
        Device device = new Device();
        device.setState(new OnState());
        device.request(); // Device is ON
        device.setState(new OffState());
        device.request(); // Device is OFF
    }
}
```

## How it works

- Device delegates behavior to current state
- Changing state changes device behavior

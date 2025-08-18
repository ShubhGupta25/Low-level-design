# Bridge Pattern - Hands-on

## Implementation Example (Java)

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
class Main {
    public static void main(String[] args) {
        Device tv = new TV();
        Remote remote = new Remote(tv);
        remote.pressButton(); // TV on
    }
}
```

## How it works

- Remote controls any device
- Device and Remote can be extended independently

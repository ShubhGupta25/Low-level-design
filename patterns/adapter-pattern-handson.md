# Adapter Pattern - Hands-on

## Implementation Example (Java)

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
class Main {
    public static void main(String[] args) {
        Adaptee adaptee = new Adaptee();
        Target target = new Adapter(adaptee);
        target.request(); // Specific request
    }
}
```

## How it works

- Adapter wraps adaptee
- Client uses target interface

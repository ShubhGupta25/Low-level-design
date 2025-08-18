# Facade Pattern

## What is it?

A structural design pattern that provides a simplified interface to a complex subsystem.

## When to Use

- Simplify complex APIs
- Hide subsystem complexity from client

## How to Use

1. Create a facade class that wraps subsystem classes
2. Facade exposes simple methods for client

## Example (Java)

```java
class CPU {
    public void start() { System.out.println("CPU started"); }
}
class Memory {
    public void load() { System.out.println("Memory loaded"); }
}
class ComputerFacade {
    private CPU cpu = new CPU();
    private Memory memory = new Memory();
    public void startComputer() {
        cpu.start();
        memory.load();
    }
}
```

## Advantages

- Simplifies client code
- Reduces dependencies

## Disadvantages

- May limit functionality
- Can become a god object

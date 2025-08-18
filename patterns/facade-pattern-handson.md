# Facade Pattern - Hands-on

## Implementation Example (Java)

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
class Main {
    public static void main(String[] args) {
        ComputerFacade computer = new ComputerFacade();
        computer.startComputer(); // CPU started, Memory loaded
    }
}
```

## How it works

- Facade wraps subsystem classes
- Client uses simple interface

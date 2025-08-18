# Null Object Pattern - Hands-on

## Implementation Example (Java)

```java
interface Animal {
    void makeSound();
}
class Dog implements Animal {
    public void makeSound() { System.out.println("Woof"); }
}
class NullAnimal implements Animal {
    public void makeSound() { /* do nothing */ }
}
class Main {
    public static void main(String[] args) {
        Animal dog = new Dog();
        Animal nullAnimal = new NullAnimal();
        dog.makeSound(); // Woof
        nullAnimal.makeSound(); // does nothing
    }
}
```

## How it works

- Null object replaces null references
- Avoids null checks and exceptions

# Null Object Pattern

## What is it?

A behavioral design pattern that uses a special object representing a "do nothing" or default behavior instead of null references.

## When to Use

- Avoid null checks and NullPointerExceptions
- Provide default behavior when no real object is available

## How to Use

1. Define an interface
2. Implement real classes and a null object class
3. Use the null object instead of null references

## Example (Java)

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
```

## Advantages

- Avoids null checks
- Simplifies code
- Provides default behavior

## Disadvantages

- May hide errors if used inappropriately
- Can add unnecessary classes

# Singleton Pattern

## What is it?

A creational design pattern that ensures a class has only one instance and provides a global point of access to it.

## When to Use

- Need a single shared resource (e.g., configuration, logger)
- Control access to a single instance

## How to Use

1. Make constructor private
2. Provide a static method to get the instance

## Example (Java)

```java
class Singleton {
    private static Singleton instance;
    private Singleton() {}
    public static Singleton getInstance() {
        if (instance == null) instance = new Singleton();
        return instance;
    }
}
```

## Advantages

- Controlled access to sole instance
- Saves resources

## Disadvantages

- Can hinder testing
- May introduce global state

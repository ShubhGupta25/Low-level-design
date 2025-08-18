# Builder Pattern

## What is it?

A creational design pattern that separates the construction of a complex object from its representation.

## When to Use

- Construct complex objects step by step
- Object creation involves many parameters

## How to Use

1. Create a builder class with methods to set properties
2. Builder returns the constructed object

## Example (Java)

```java
class Pizza {
    private String dough;
    private String topping;
    private Pizza(String dough, String topping) {
        this.dough = dough;
        this.topping = topping;
    }
    public static class Builder {
        private String dough;
        private String topping;
        public Builder setDough(String dough) { this.dough = dough; return this; }
        public Builder setTopping(String topping) { this.topping = topping; return this; }
        public Pizza build() { return new Pizza(dough, topping); }
    }
}
```

## Advantages

- Simplifies object creation
- Supports immutability

## Disadvantages

- More classes
- Can be overkill for simple objects

# Decorator Pattern

## What is it?

A structural design pattern that allows you to add new functionality to objects dynamically without altering their structure.

## When to Use

- Add responsibilities to individual objects
- Extension by subclassing is impractical
- Add features dynamically at runtime

## How to Use

1. Define a common interface for core component and decorators
2. Create concrete component classes
3. Create abstract decorator class holding a reference to a component
4. Concrete decorators extend the abstract decorator and add new behavior

## Example (Java)

```java
interface Pizza {
    String getDescription();
    double getCost();
}
class Margherita implements Pizza {
    public String getDescription() { return "Margherita"; }
    public double getCost() { return 100; }
}
abstract class PizzaDecorator implements Pizza {
    protected Pizza pizza;
    public PizzaDecorator(Pizza pizza) { this.pizza = pizza; }
}
class Cheese extends PizzaDecorator {
    public Cheese(Pizza pizza) { super(pizza); }
    public String getDescription() { return pizza.getDescription() + ", Cheese"; }
    public double getCost() { return pizza.getCost() + 20; }
}
```

## Advantages

- Add functionality without modifying existing code
- More flexible than inheritance
- Add/remove features at runtime

## Disadvantages

- Can result in many small classes
- Complexity increases with many decorators

# Design Pizza Billing System

## Problem Statement

Implement a pizza ordering system where users can add multiple toppings and get the final bill.

## Key Concepts

- Decorator Pattern: Add toppings dynamically to a pizza object.
- Extensibility: Easy to add new toppings.

## Example (Java)

```java
interface Pizza {
    int getCost();
}
class Margherita implements Pizza {
    public int getCost() { return 100; }
}
abstract class ToppingDecorator implements Pizza {
    protected Pizza pizza;
    public ToppingDecorator(Pizza pizza) { this.pizza = pizza; }
}
class Cheese extends ToppingDecorator {
    public Cheese(Pizza pizza) { super(pizza); }
    public int getCost() { return pizza.getCost() + 20; }
}
class Olives extends ToppingDecorator {
    public Olives(Pizza pizza) { super(pizza); }
    public int getCost() { return pizza.getCost() + 15; }
}
```

## When to Use

- Customizable products/services
- Billing systems, e-commerce, etc.

## Advantages

- Flexible, extensible
- No need for many subclasses

## Disadvantages

- Many small classes
- Can be complex for large systems

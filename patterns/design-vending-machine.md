# Design Vending Machine

## Problem Statement

Implement a vending machine system that dispenses products, accepts payments, and manages inventory.

## Key Concepts

- State Pattern: Machine states (idle, dispensing, out of stock)
- Strategy Pattern: Payment methods

## Example (Java)

```java
class VendingMachine {
    private String state;
    public void insertCoin() { /* ... */ }
    public void selectProduct(String product) { /* ... */ }
    public void dispense() { /* ... */ }
}
interface PaymentStrategy {
    void pay(int amount);
}
class CashPayment implements PaymentStrategy {
    public void pay(int amount) { /* ... */ }
}
```

## When to Use

- Automated retail systems
- Systems with multiple states and payment options

## Advantages

- Modular, extensible
- Supports multiple payment methods

## Disadvantages

- Can be complex
- Requires careful state management

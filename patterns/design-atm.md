# Design ATM

## Problem Statement

Implement an ATM system that handles user authentication, transactions, and cash dispensing.

## Key Concepts

- State Pattern: ATM states (idle, authenticating, dispensing)
- Strategy Pattern: Transaction types (withdraw, deposit)

## Example (Java)

```java
class ATM {
    private String state;
    public void authenticate(String card, String pin) { /* ... */ }
    public void withdraw(int amount) { /* ... */ }
    public void deposit(int amount) { /* ... */ }
}
interface TransactionStrategy {
    void execute(int amount);
}
class WithdrawStrategy implements TransactionStrategy {
    public void execute(int amount) { /* ... */ }
}
```

## When to Use

- Banking systems
- Systems with multiple transaction types

## Advantages

- Modular, extensible
- Supports multiple transaction types

## Disadvantages

- Can be complex
- Requires integration with banking systems

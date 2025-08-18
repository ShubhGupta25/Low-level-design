# Design Payment System

## Problem Statement

Implement a payment system supporting multiple payment methods, transaction processing, and notifications.

## Key Concepts

- Strategy Pattern: Payment methods (credit card, UPI, wallet)
- Observer Pattern: Transaction notifications
- Object-Oriented Design: Classes for Payment, Transaction, Notification

## Example (Java)

```java
interface PaymentStrategy {
    void pay(double amount);
}
class CreditCardPayment implements PaymentStrategy {
    public void pay(double amount) { /* ... */ }
}
class UpiPayment implements PaymentStrategy {
    public void pay(double amount) { /* ... */ }
}
class Transaction {
    private double amount;
    private PaymentStrategy paymentStrategy;
    public void process() { paymentStrategy.pay(amount); }
}
```

## When to Use

- E-commerce, banking, fintech
- Systems with multiple payment options

## Advantages

- Modular, extensible
- Supports multiple payment methods

## Disadvantages

- Can be complex
- Requires integration with external services

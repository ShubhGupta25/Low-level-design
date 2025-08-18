# Design Car Rental System

## Problem Statement

Implement a car rental system supporting vehicle inventory, booking, and payment.

## Key Concepts

- Object-Oriented Design: Classes for Car, Booking, Payment
- Factory Pattern: Create car objects
- Strategy Pattern: Pricing strategies

## Example (Java)

```java
class Car {
    private String type;
    private boolean available;
}
class Booking {
    private Car car;
    private String user;
}
interface PaymentStrategy {
    void pay(double amount);
}
class CreditCardPayment implements PaymentStrategy {
    public void pay(double amount) { /* ... */ }
}
```

## When to Use

- Rental management systems
- Systems with inventory and booking

## Advantages

- Modular, extensible
- Supports multiple payment methods

## Disadvantages

- Can be complex
- Requires integration with payment gateways

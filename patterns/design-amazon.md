# Design Amazon

## Problem Statement

Implement a simplified e-commerce platform like Amazon, supporting product catalog, cart, order, and payment.

## Key Concepts

- Object-Oriented Design: Classes for Product, Cart, Order, Payment
- Strategy Pattern: Payment methods
- Observer Pattern: Order status notifications

## Example (Java)

```java
class Product {
    private String name;
    private double price;
}
class Cart {
    private List<Product> products;
    public void addProduct(Product product) { /* ... */ }
}
class Order {
    private Cart cart;
    private String status;
}
interface PaymentStrategy {
    void pay(double amount);
}
class CreditCardPayment implements PaymentStrategy {
    public void pay(double amount) { /* ... */ }
}
```

## When to Use

- E-commerce platforms
- Systems with multiple payment and notification options

## Advantages

- Modular, extensible
- Supports multiple payment and notification methods

## Disadvantages

- Can be complex
- Requires integration with external services

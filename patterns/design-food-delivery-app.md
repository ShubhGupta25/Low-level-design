# Design Food Delivery App (Swiggy/Zomato)

## Problem Statement

Implement a food delivery app supporting restaurants, orders, delivery tracking, and payments.

## Key Concepts

- Object-Oriented Design: Classes for Restaurant, Order, Delivery, Payment
- Strategy Pattern: Delivery assignment, payment methods
- Observer Pattern: Order status notifications

## Example (Java)

```java
class Restaurant {
    private String name;
    private List<MenuItem> menu;
}
class Order {
    private Restaurant restaurant;
    private List<MenuItem> items;
    private String status;
}
class Delivery {
    private Order order;
    private String status;
}
```

## When to Use

- Food delivery platforms
- Systems with real-time tracking and notifications

## Advantages

- Modular, extensible
- Supports multiple payment and notification methods

## Disadvantages

- Can be complex
- Requires integration with external services

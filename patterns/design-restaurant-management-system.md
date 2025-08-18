# Design Restaurant Management System

## Problem Statement

Implement a restaurant management system supporting menu, orders, billing, and inventory.

## Key Concepts

- Object-Oriented Design: Classes for Menu, Order, Bill, Inventory
- Strategy Pattern: Billing and discount strategies
- Observer Pattern: Inventory notifications

## Example (Java)

```java
class Menu {
    private List<MenuItem> items;
}
class Order {
    private List<MenuItem> items;
    private double total;
}
class Inventory {
    private Map<MenuItem, Integer> stock;
}
class Bill {
    private Order order;
    private double amount;
}
```

## When to Use

- Restaurant management platforms
- Systems with inventory and billing

## Advantages

- Modular, extensible
- Supports multiple billing and notification methods

## Disadvantages

- Can be complex
- Requires integration with external systems

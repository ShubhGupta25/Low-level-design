# Design Stock Exchange System

## Problem Statement

Implement a stock exchange system supporting order matching, trade execution, and market data.

## Key Concepts

- Object-Oriented Design: Classes for Order, Trade, MarketData
- Observer Pattern: Market data updates
- Strategy Pattern: Order matching algorithms

## Example (Java)

```java
class Order {
    private String type;
    private double price;
    private int quantity;
}
class Trade {
    private Order buyOrder;
    private Order sellOrder;
}
class MarketData {
    private List<Order> orders;
}
```

## When to Use

- Financial trading platforms
- Systems with real-time data and matching algorithms

## Advantages

- Modular, extensible
- Supports multiple matching algorithms

## Disadvantages

- Can be complex
- Requires high performance and reliability

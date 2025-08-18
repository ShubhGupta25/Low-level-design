# Design Airline Management System

## Problem Statement

Implement an airline management system supporting flight scheduling, booking, and passenger management.

## Key Concepts

- Object-Oriented Design: Classes for Flight, Booking, Passenger
- Strategy Pattern: Pricing and seat allocation
- Observer Pattern: Flight status notifications

## Example (Java)

```java
class Flight {
    private String flightNumber;
    private List<Passenger> passengers;
}
class Booking {
    private Flight flight;
    private Passenger passenger;
}
class Passenger {
    private String name;
}
```

## When to Use

- Airline reservation systems
- Systems with scheduling and notifications

## Advantages

- Modular, extensible
- Supports multiple features

## Disadvantages

- Can be complex
- Requires integration with external systems

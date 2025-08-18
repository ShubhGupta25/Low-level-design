# Design BookMyShow & Concurrency Handling

## Problem Statement

Implement a ticket booking system (like BookMyShow) with concurrency handling for seat reservations.

## Key Concepts

- Object-Oriented Design: Classes for Show, Seat, Booking
- Concurrency: Locking, atomic operations

## Example (Java)

```java
class Show {
    private List<Seat> seats;
}
class Seat {
    private boolean booked;
    public synchronized boolean book() {
        if (!booked) {
            booked = true;
            return true;
        }
        return false;
    }
}
class Booking {
    private Show show;
    private Seat seat;
}
```

## When to Use

- Ticketing systems
- Systems with concurrent resource access

## Advantages

- Prevents double booking
- Ensures data consistency

## Disadvantages

- Requires careful concurrency management
- Can be complex for large systems

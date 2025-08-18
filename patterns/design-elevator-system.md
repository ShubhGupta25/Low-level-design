# Design Elevator System

## Problem Statement

Implement an elevator system that handles multiple elevators, requests, and scheduling.

## Key Concepts

- Object-Oriented Design: Classes for Elevator, Request, Scheduler
- State Pattern: Elevator state (moving, idle, maintenance)
- Strategy Pattern: Scheduling algorithms (nearest, optimal)

## Example (Java)

```java
class Elevator {
    private int currentFloor;
    private String state; // moving, idle, maintenance
    public void moveTo(int floor) { /* ... */ }
}
class Request {
    private int sourceFloor;
    private int destinationFloor;
}
interface Scheduler {
    void schedule(Request request);
}
class NearestScheduler implements Scheduler {
    public void schedule(Request request) { /* ... */ }
}
```

## When to Use

- Building management systems
- Systems with resource scheduling

## Advantages

- Modular, extensible
- Supports multiple algorithms

## Disadvantages

- Can be complex
- Requires careful state management

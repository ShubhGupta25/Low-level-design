# Design Calendar Application

## Problem Statement

Implement a calendar application supporting events, reminders, and scheduling.

## Key Concepts

- Object-Oriented Design: Classes for Event, Reminder, Calendar
- Observer Pattern: Reminder notifications
- Strategy Pattern: Scheduling algorithms

## Example (Java)

```java
class Event {
    private String title;
    private String date;
}
class Reminder {
    private Event event;
    private String time;
}
class Calendar {
    private List<Event> events;
}
```

## When to Use

- Scheduling and reminder applications
- Systems with notifications and scheduling

## Advantages

- Modular, extensible
- Supports multiple scheduling algorithms

## Disadvantages

- Can be complex
- Requires integration with external systems

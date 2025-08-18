# Design Notify-Me Button Functionality

## Problem Statement

Implement a system where users can subscribe to notifications for a specific event (e.g., product back in stock, next stage counseling).

## Key Concepts

- Observer Pattern: Users (observers) subscribe to an event (subject) and get notified when the event occurs.
- Decoupling: The event generator and subscribers are loosely coupled.

## Example (Java)

```java
interface Observer {
    void notify(String message);
}
class User implements Observer {
    private String name;
    public User(String name) { this.name = name; }
    public void notify(String message) {
        System.out.println(name + " notified: " + message);
    }
}
class Event {
    private List<Observer> observers = new ArrayList<>();
    public void subscribe(Observer observer) { observers.add(observer); }
    public void notifyAll(String message) {
        for (Observer o : observers) o.notify(message);
    }
}
```

## When to Use

- Any system where users subscribe to updates/events
- E-commerce, education, ticketing, etc.

## Advantages

- Decouples event source and listeners
- Easy to add/remove subscribers

## Disadvantages

- Can lead to memory leaks if not managed
- Notification to many users may impact performance

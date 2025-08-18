# Factory Pattern

## What is it?

A creational design pattern that provides an interface for creating objects, letting subclasses decide which class to instantiate.

## When to Use

- Object creation logic is complex or varies
- Decouple object creation from usage
- Centralize creation of related objects

## How to Use

1. Define a common interface or abstract class
2. Implement concrete classes for each object type
3. Create a factory class with a method to return objects based on input/configuration

## Example (Java)

```java
interface Notification {
    void notifyUser();
}
class EmailNotification implements Notification {
    public void notifyUser() { System.out.println("Sending Email Notification"); }
}
class SMSNotification implements Notification {
    public void notifyUser() { System.out.println("Sending SMS Notification"); }
}
class NotificationFactory {
    public static Notification createNotification(String type) {
        if (type.equalsIgnoreCase("EMAIL")) return new EmailNotification();
        else if (type.equalsIgnoreCase("SMS")) return new SMSNotification();
        throw new IllegalArgumentException("Unknown notification type");
    }
}
```

## Advantages

- Encapsulates object creation
- Promotes loose coupling
- Flexible and maintainable

## Disadvantages

- Can introduce extra classes
- May be less efficient for simple cases

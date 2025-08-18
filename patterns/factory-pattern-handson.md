# Factory Pattern - Hands-on

## Implementation Example (Java)

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
class Main {
    public static void main(String[] args) {
        Notification notification = NotificationFactory.createNotification("EMAIL");
        notification.notifyUser();
    }
}
```

## How it works

- Factory creates objects based on input
- Client uses factory, not concrete classes

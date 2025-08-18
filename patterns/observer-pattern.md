# Observer Pattern in Low Level Design (LLD)

## What is the Observer Pattern?

The Observer Pattern is a behavioral design pattern where an object (the subject) maintains a list of dependents (observers) and notifies them automatically of any state changes, usually by calling one of their methods. It is also known as the Publish-Subscribe pattern.

---

## When to Use

- When an object's state change needs to be communicated to other objects automatically.
- When you want to decouple the subject from its observers.
- Common in event-driven systems, GUIs, and real-time data feeds.

---

## How to Use

1. Define a Subject interface with methods to attach, detach, and notify observers.
2. Define an Observer interface with an update method.
3. Concrete Subject maintains a list of observers and notifies them of changes.
4. Concrete Observers implement the update method to react to changes.

---

## Example (Java)

```java
// Observer interface
public interface Observer {
    void update(String message);
}
// Concrete Observer
public class User implements Observer {
    private String name;
    public User(String name) { this.name = name; }
    public void update(String message) {
        System.out.println(name + " received notification: " + message);
    }
}
// Subject interface
public interface Subject {
    void attach(Observer o);
    void detach(Observer o);
    void notifyObservers(String message);
}
// Concrete Subject
public class Product implements Subject {
    private List<Observer> observers = new ArrayList<>();
    public void attach(Observer o) { observers.add(o); }
    public void detach(Observer o) { observers.remove(o); }
    public void notifyObservers(String message) {
        for (Observer o : observers) {
            o.update(message);
        }
    }
    // Business logic
    public void backInStock() {
        notifyObservers("Product is back in stock!");
    }
}
// Usage
public class Main {
    public static void main(String[] args) {
        Product product = new Product();
        User user1 = new User("Alice");
        User user2 = new User("Bob");
        product.attach(user1);
        product.attach(user2);
        product.backInStock();
    }
}
```

---

## Advantages

- Promotes loose coupling between subject and observers.
- Easy to add or remove observers at runtime.
- Useful for implementing event-driven systems.

---

## Disadvantages

- Can lead to memory leaks if observers are not properly removed.
- Notification to a large number of observers may impact performance.
- Debugging can be harder due to dynamic relationships.

---

## Hands-on Example

```java
// Observer interface
interface Observer {
    void notify(String message);
}
// Student class as Observer
class Student implements Observer {
    private String firstName;
    private String lastName;
    public void notify(String message) {
        System.out.println(firstName + " notified for: " + message);
    }
}
// Subject interface
interface Subject {
    void subscribe(Observer observer);
    void unSubscribe(Observer observer);
    void notifyObservers(String message);
}
// Subject implementation
class EnrolledStudentNotifier implements Subject {
    private List<Observer> enrolledStudents = new ArrayList<>();
    public void subscribe(Observer observer) { enrolledStudents.add(observer); }
    public void unSubscribe(Observer observer) { enrolledStudents.remove(observer); }
    public void notifyObservers(String message) {
        for (Observer observer : enrolledStudents) {
            observer.notify(message);
        }
    }
}
```

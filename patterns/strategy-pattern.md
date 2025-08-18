# Strategy Pattern in Low Level Design (LLD)

## What is the Strategy Pattern?

The Strategy Pattern is a behavioral design pattern that enables selecting an algorithm’s behavior at runtime. It defines a family of algorithms, encapsulates each one, and makes them interchangeable. The pattern lets the algorithm vary independently from clients that use it.

---

## When to Use

- Multiple ways of performing an operation (e.g., different sorting or payment methods)
- Avoid many conditional statements to select behaviors
- Make code more flexible and extensible

---

## How to Use

1. Define a common interface for all supported algorithms (strategies)
2. Implement concrete strategy classes for each algorithm
3. Context class maintains a reference to a strategy object and delegates the work to it
4. Client can change the strategy at runtime

---

## Example (Java)

```java
// Strategy interface
public interface PaymentStrategy {
    void pay(int amount);
}
// Concrete strategies
public class CreditCardPayment implements PaymentStrategy {
    public void pay(int amount) {
        System.out.println("Paid " + amount + " using Credit Card.");
    }
}
public class PayPalPayment implements PaymentStrategy {
    public void pay(int amount) {
        System.out.println("Paid " + amount + " using PayPal.");
    }
}
// Context
public class ShoppingCart {
    private PaymentStrategy paymentStrategy;
    public void setPaymentStrategy(PaymentStrategy strategy) {
        this.paymentStrategy = strategy;
    }
    public void checkout(int amount) {
        paymentStrategy.pay(amount);
    }
}
// Usage
public class Main {
    public static void main(String[] args) {
        ShoppingCart cart = new ShoppingCart();
        cart.setPaymentStrategy(new CreditCardPayment());
        cart.checkout(100);
        cart.setPaymentStrategy(new PayPalPayment());
        cart.checkout(200);
    }
}
```

---

## Advantages

- Promotes Open/Closed Principle
- Eliminates complex conditional statements
- Strategies can be changed at runtime

---

## Disadvantages

- Increases the number of classes
- Client must be aware of different strategies

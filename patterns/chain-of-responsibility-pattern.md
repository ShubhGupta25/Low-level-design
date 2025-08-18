# Chain of Responsibility Pattern

## What is it?

A behavioral design pattern that lets a request pass through a chain of handlers. Each handler decides to process or pass the request further.

## When to Use

- Multiple objects can handle a request, but handler is not known in advance.
- Decouple sender and receiver.
- Sequential processing (validation, authorization, etc).

## How to Use

1. Define a handler interface/abstract class with a method to process requests and a reference to the next handler.
2. Implement concrete handlers.
3. Link handlers to form a chain.
4. Client sends request to first handler.

## Example (Java)

```java
abstract class Handler {
    protected Handler next;
    public void setNext(Handler next) { this.next = next; }
    public abstract void handle(String req);
}
class AuthHandler extends Handler {
    public void handle(String req) {
        if (req.equals("auth")) System.out.println("Auth handled");
        else if (next != null) next.handle(req);
    }
}
class LogHandler extends Handler {
    public void handle(String req) {
        if (req.equals("log")) System.out.println("Log handled");
        else if (next != null) next.handle(req);
    }
}
```

## Advantages

- Decouples sender/receiver
- Flexible chain structure
- Single responsibility per handler

## Disadvantages

- Request may go unhandled
- Debugging can be harder
- Performance overhead if chain is long

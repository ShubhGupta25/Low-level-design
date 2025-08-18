# Chain of Responsibility Pattern - Hands-on

## Implementation Example (Java)

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
class Main {
    public static void main(String[] args) {
        Handler auth = new AuthHandler();
        Handler log = new LogHandler();
        auth.setNext(log);
        auth.handle("auth"); // Auth handled
        auth.handle("log");  // Log handled
    }
}
```

## How it works

- Handlers are linked in a chain.
- Each handler checks if it can process the request, else passes to next.
- Flexible to add/remove handlers.

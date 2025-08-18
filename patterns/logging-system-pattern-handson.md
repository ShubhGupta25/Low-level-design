# Logging System Pattern - Hands-on

## Implementation Example (Java)

```java
class Logger {
    private static Logger instance = new Logger();
    private Logger() {}
    public static Logger getInstance() { return instance; }
    public void log(String msg) { System.out.println(msg); }
}
class Main {
    public static void main(String[] args) {
        Logger logger = Logger.getInstance();
        logger.log("App started");
        logger.log("App finished");
    }
}
```

## How it works

- Logger is a singleton
- Used throughout the app for logging

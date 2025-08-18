# Proxy Pattern

## What is it?

A structural design pattern that provides a surrogate or placeholder for another object to control access to it.

## When to Use

- Control access to an object (authentication, authorization)
- Add logging, caching, lazy loading
- Work with expensive/remote resources

## How to Use

1. Define an interface for the subject
2. Implement the real subject class
3. Implement a proxy class that implements the same interface and holds a reference to the real subject
4. Proxy adds extra behavior and delegates requests

## Example (Java)

```java
interface Resource {
    void access();
}
class RealResource implements Resource {
    public void access() { System.out.println("Accessing real resource"); }
}
class ResourceProxy implements Resource {
    private RealResource realResource;
    private boolean isAuthorized;
    public ResourceProxy(boolean isAuthorized) {
        this.realResource = new RealResource();
        this.isAuthorized = isAuthorized;
    }
    public void access() {
        if (isAuthorized) {
            System.out.println("Proxy: Authorization successful");
            realResource.access();
        } else {
            System.out.println("Proxy: Access denied");
        }
    }
}
```

## Advantages

- Controls access
- Adds extra functionality
- Supports lazy initialization

## Disadvantages

- Adds complexity
- May introduce performance overhead
- Client may need to be aware of proxy

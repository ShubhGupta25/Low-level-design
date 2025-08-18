# Proxy Pattern - Hands-on

## Implementation Example (Java)

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
class Main {
    public static void main(String[] args) {
        Resource resource = new ResourceProxy(true);
        resource.access(); // Authorized access
        Resource resource2 = new ResourceProxy(false);
        resource2.access(); // Access denied
    }
}
```

## How it works

- Proxy controls access to the real object
- Can add logging, caching, etc. transparently

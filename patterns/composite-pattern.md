# Composite Pattern

## What is it?

A structural design pattern that lets you compose objects into tree structures to represent part-whole hierarchies.

## When to Use

- Represent tree structures (e.g., file system, UI components)
- Treat individual objects and compositions uniformly

## How to Use

1. Define a component interface
2. Implement leaf and composite classes
3. Composite class holds child components

## Example (Java)

```java
interface Component {
    void show();
}
class Leaf implements Component {
    public void show() { System.out.println("Leaf"); }
}
class Composite implements Component {
    private List<Component> children = new ArrayList<>();
    public void add(Component c) { children.add(c); }
    public void show() {
        for (Component c : children) c.show();
    }
}
```

## Advantages

- Simplifies client code
- Supports recursive structures
- Uniform treatment of objects

## Disadvantages

- Can make design more complex
- May be hard to restrict composite usage

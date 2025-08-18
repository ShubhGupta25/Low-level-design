# Composite Pattern - Hands-on

## Implementation Example (Java)

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
class Main {
    public static void main(String[] args) {
        Composite root = new Composite();
        root.add(new Leaf());
        Composite branch = new Composite();
        branch.add(new Leaf());
        root.add(branch);
        root.show(); // Leaf Leaf
    }
}
```

## How it works

- Composite holds children
- show() calls show() on all children

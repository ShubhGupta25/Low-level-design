# Abstract Factory Pattern

## What is it?

A creational design pattern that provides an interface for creating families of related or dependent objects without specifying their concrete classes.

## When to Use

- Create families of related objects
- Enforce consistency among products
- Decouple client code from concrete classes

## How to Use

1. Define abstract product interfaces
2. Create concrete product classes
3. Define an abstract factory interface
4. Implement concrete factory classes for each family
5. Client uses abstract factory to create products

## Example (Java)

```java
interface Button { void paint(); }
interface Checkbox { void paint(); }
class WindowsButton implements Button {
    public void paint() { System.out.println("Windows Button"); }
}
class WindowsCheckbox implements Checkbox {
    public void paint() { System.out.println("Windows Checkbox"); }
}
class MacButton implements Button {
    public void paint() { System.out.println("Mac Button"); }
}
class MacCheckbox implements Checkbox {
    public void paint() { System.out.println("Mac Checkbox"); }
}
interface GUIFactory {
    Button createButton();
    Checkbox createCheckbox();
}
class WindowsFactory implements GUIFactory {
    public Button createButton() { return new WindowsButton(); }
    public Checkbox createCheckbox() { return new WindowsCheckbox(); }
}
class MacFactory implements GUIFactory {
    public Button createButton() { return new MacButton(); }
    public Checkbox createCheckbox() { return new MacCheckbox(); }
}
```

## Advantages

- Ensures consistency among products
- Promotes loose coupling
- Easy to introduce new families

## Disadvantages

- Adding new product types requires changing all factories
- Can introduce complexity

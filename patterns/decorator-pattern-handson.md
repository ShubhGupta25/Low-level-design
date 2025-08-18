# Decorator Pattern - Hands-on

## Implementation Example (Java)

```java
interface Pizza {
    Integer billAmount();
}
class Margherita implements Pizza {
    private Integer amount = 100;
    public Integer billAmount() { return amount; }
}
abstract class PizzaToppings implements Pizza {
    private Pizza pizza;
    PizzaToppings(Pizza pizza) { this.pizza = pizza; }
    public Pizza getPizza() { return pizza; }
}
class OliveTopping extends PizzaToppings {
    private Integer toppingPrice = 50;
    OliveTopping(Pizza pizza) { super(pizza); }
    public Integer billAmount() { return getPizza().billAmount() + toppingPrice; }
}
class Main {
    public static void main(String[] args) {
        Pizza order1 = new Margherita();
        Pizza order2 = new OliveTopping(new Margherita());
        System.out.println(order1.billAmount()); // 100
        System.out.println(order2.billAmount()); // 150
    }
}
```

## How it works

- Decorators wrap core objects and add new behavior

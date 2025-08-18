# Builder Pattern - Hands-on

## Implementation Example (Java)

```java
class Pizza {
    private String dough;
    private String topping;
    private Pizza(String dough, String topping) {
        this.dough = dough;
        this.topping = topping;
    }
    public static class Builder {
        private String dough;
        private String topping;
        public Builder setDough(String dough) { this.dough = dough; return this; }
        public Builder setTopping(String topping) { this.topping = topping; return this; }
        public Pizza build() { return new Pizza(dough, topping); }
    }
}
class Main {
    public static void main(String[] args) {
        Pizza pizza = new Pizza.Builder().setDough("Thin").setTopping("Cheese").build();
        System.out.println("Pizza created");
    }
}
```

## How it works

- Builder sets properties and builds the object

# Interpreter Pattern - Hands-on

## Implementation Example (Java)

```java
interface Expression {
    int interpret();
}
class Number implements Expression {
    private int number;
    public Number(int number) { this.number = number; }
    public int interpret() { return number; }
}
class Add implements Expression {
    private Expression left, right;
    public Add(Expression left, Expression right) {
        this.left = left; this.right = right;
    }
    public int interpret() { return left.interpret() + right.interpret(); }
}
class Main {
    public static void main(String[] args) {
        Expression expr = new Add(new Number(2), new Number(3));
        System.out.println(expr.interpret()); // 5
    }
}
```

## How it works

- Expressions are composed and interpreted

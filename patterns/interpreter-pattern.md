# Interpreter Pattern

## What is it?

A behavioral design pattern that defines a grammar for interpreting sentences of a language.

## When to Use

- Implement simple languages or expressions
- Parse and evaluate expressions

## How to Use

1. Define an abstract expression interface
2. Implement concrete expression classes
3. Context holds input and invokes interpret

## Example (Java)

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
```

## Advantages

- Easy to extend grammar
- Good for simple languages

## Disadvantages

- Not efficient for complex grammars
- Can be hard to maintain

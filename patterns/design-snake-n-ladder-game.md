# Design Snake n Ladder Game

## Problem Statement

Implement a Snake and Ladder game supporting different board types, dice, and rules.

## Key Concepts

- Abstract Factory Pattern: Create families of related objects (board, dice, rules).
- Extensibility: Easy to add new game variants.

## Example (Java)

```java
interface Board {}
class ClassicBoard implements Board {}
class CustomBoard implements Board {}
interface Dice {
    int roll();
}
class RegularDice implements Dice {
    public int roll() { return (int)(Math.random() * 6) + 1; }
}
interface Rule {}
interface GameFactory {
    Board createBoard();
    Dice createDice();
    Rule createRule();
}
class ClassicGameFactory implements GameFactory {
    public Board createBoard() { return new ClassicBoard(); }
    public Dice createDice() { return new RegularDice(); }
    public Rule createRule() { return null; }
}
```

## When to Use

- Games with multiple variants
- Systems needing consistency among related objects

## Advantages

- Consistent product families
- Easy to extend

## Disadvantages

- More classes and interfaces
- Can be complex

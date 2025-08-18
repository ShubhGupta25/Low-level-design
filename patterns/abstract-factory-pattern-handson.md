# Abstract Factory Pattern - Hands-on

## Implementation Example (Java)

```java
interface Board {}
class ClassicBoard implements Board {
    private int snakes = 10;
    private int ladders = 10;
}
class CustomBoard implements Board {
    private int snakes;
    private int ladders;
    public CustomBoard(int snakes, int ladders) {
        this.snakes = snakes;
        this.ladders = ladders;
    }
}
interface Dice {
    int rollANumber();
}
class RegularDice implements Dice {
    private int sides = 6;
    public int rollANumber() { return (int)(Math.random() * sides) + 1; }
}
interface Rule {
    // ... rule logic
}
interface GameFactory {
    Board setupBoard();
    Rule setupRules();
    Dice setupDice();
}
class ClassicGameFactory implements GameFactory {
    public Board setupBoard() { return new ClassicBoard(); }
    public Dice setupDice() { return new RegularDice(); }
    public Rule setupRules() { return null; }
}
```

## How it works

- Factory creates families of related objects
- Client uses factory for all products

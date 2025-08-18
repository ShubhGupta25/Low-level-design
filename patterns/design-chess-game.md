# Design Chess Game

## Problem Statement

Implement a chess game supporting board state, player moves, and win/draw detection.

## Key Concepts

- Object-Oriented Design: Classes for Board, Player, Piece, Game
- State Pattern: Board and piece state management

## Example (Java)

```java
class Board {
    private Piece[][] grid = new Piece[8][8];
}
class Piece {
    private String type;
    private String color;
}
class Player {
    private String color;
}
class Game {
    private Board board;
    private Player player1, player2;
    public void play() { /* ... */ }
}
```

## When to Use

- Board games
- Educational projects

## Advantages

- Modular, extensible
- Good for learning OOP

## Disadvantages

- Complex rules
- Requires careful state management

# Design Tic-Tac-Toe Game

## Problem Statement

Implement a Tic-Tac-Toe game supporting two players, board state, and win/draw detection.

## Key Concepts

- Object-Oriented Design: Classes for Board, Player, Game
- State Pattern: Board state management

## Example (Java)

```java
class Board {
    private char[][] grid = new char[3][3];
    public boolean isWin() { /* ... */ }
    public boolean isDraw() { /* ... */ }
}
class Player {
    private char symbol;
}
class Game {
    private Board board;
    private Player player1, player2;
    public void play() { /* ... */ }
}
```

## When to Use

- Simple board games
- Educational projects

## Advantages

- Simple, easy to implement
- Good for learning OOP

## Disadvantages

- Limited complexity
- Not suitable for large-scale games

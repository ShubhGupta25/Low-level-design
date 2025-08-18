# Design Bowling Alley Machine

## Problem Statement

Implement a bowling alley machine system supporting lane management, scoring, and game tracking.

## Key Concepts

- Object-Oriented Design: Classes for Lane, Game, Score
- State Pattern: Lane and game states
- Strategy Pattern: Scoring algorithms

## Example (Java)

```java
class Lane {
    private int number;
    private String state;
}
class Game {
    private Lane lane;
    private List<Player> players;
}
class Score {
    private Player player;
    private int points;
}
```

## When to Use

- Bowling alley management
- Systems with game tracking and scoring

## Advantages

- Modular, extensible
- Supports multiple scoring algorithms

## Disadvantages

- Can be complex
- Requires integration with hardware

# SOLID Principles in Low Level Design (LLD)

## Overview

SOLID is an acronym for five design principles intended to make software designs more understandable, flexible, and maintainable. These principles are widely used in object-oriented design and are fundamental for building robust systems.

---

## Principles

- **Single Responsibility Principle (SRP):** A class should have only one reason to change.
- **Open/Closed Principle (OCP):** Software entities should be open for extension but closed for modification.
- **Liskov Substitution Principle (LSP):** Subtypes must be substitutable for their base types.
- **Interface Segregation Principle (ISP):** No client should be forced to depend on methods it does not use.
- **Dependency Inversion Principle (DIP):** High-level modules should not depend on low-level modules; both should depend on abstractions.

---

## When to Use

- When designing maintainable, flexible, and scalable systems
- When refactoring legacy code

---

## How to Use

- Refactor classes to have single responsibilities
- Use interfaces and abstractions
- Split large interfaces into smaller ones
- Use dependency injection

---

## Advantages

- Easier to maintain, test, and understand
- Promotes code reusability and flexibility
- Reduces risk of bugs when making changes

---

## Disadvantages

- May lead to more classes and interfaces
- Can introduce complexity

---

## Summary Table

| Principle | When to Use                         | How to Use                                  | Advantages         | Disadvantages     |
| --------- | ----------------------------------- | ------------------------------------------- | ------------------ | ----------------- |
| SRP       | Class has multiple responsibilities | Refactor into single-responsibility classes | Easier maintenance | More classes      |
| OCP       | Anticipate future changes           | Use abstraction, inheritance                | Flexible, reusable | More abstractions |
| LSP       | Using inheritance                   | Ensure substitutability                     | Reliable code      | Hard to enforce   |
| ISP       | Large interfaces                    | Split into smaller interfaces               | Flexible, clear    | More interfaces   |
| DIP       | Tight coupling                      | Depend on abstractions                      | Loose coupling     | More boilerplate  |

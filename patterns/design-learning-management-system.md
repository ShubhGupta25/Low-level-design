# Design Learning Management System

## Problem Statement

Implement a learning management system supporting courses, students, assignments, and grading.

## Key Concepts

- Object-Oriented Design: Classes for Course, Student, Assignment, Grade
- Observer Pattern: Assignment notifications
- Strategy Pattern: Grading algorithms

## Example (Java)

```java
class Course {
    private String name;
    private List<Student> students;
}
class Student {
    private String name;
}
class Assignment {
    private String title;
    private Course course;
}
class Grade {
    private Student student;
    private Assignment assignment;
    private double score;
}
```

## When to Use

- Educational platforms
- Systems with notifications and grading

## Advantages

- Modular, extensible
- Supports multiple grading algorithms

## Disadvantages

- Can be complex
- Requires integration with external systems

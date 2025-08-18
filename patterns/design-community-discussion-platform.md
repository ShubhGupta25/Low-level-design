# Design Community Discussion Platform

## Problem Statement

Implement a community discussion platform supporting topics, posts, comments, and notifications.

## Key Concepts

- Object-Oriented Design: Classes for Topic, Post, Comment, User
- Observer Pattern: Notifications for new posts/comments

## Example (Java)

```java
class Topic {
    private String title;
    private List<Post> posts;
}
class Post {
    private String content;
    private User author;
}
class Comment {
    private String content;
    private User author;
}
```

## When to Use

- Forums, Q&A platforms
- Systems with notifications and discussions

## Advantages

- Modular, extensible
- Supports multiple notification types

## Disadvantages

- Can be complex
- Requires moderation and spam control

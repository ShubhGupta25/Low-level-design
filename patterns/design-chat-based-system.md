# Design Chat Based System

## Problem Statement

Implement a chat-based system supporting messaging, user presence, and notifications.

## Key Concepts

- Observer Pattern: Message and presence notifications
- Object-Oriented Design: Classes for User, Message, ChatRoom

## Example (Java)

```java
class User {
    private String name;
}
class Message {
    private String content;
    private User sender;
}
class ChatRoom {
    private List<User> users;
    public void sendMessage(Message message) { /* ... */ }
}
```

## When to Use

- Messaging platforms
- Systems with real-time notifications

## Advantages

- Modular, extensible
- Supports multiple notification types

## Disadvantages

- Can be complex
- Requires real-time infrastructure

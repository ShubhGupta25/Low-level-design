# Design File System

## Problem Statement

Implement a file system supporting files, folders, and operations like create, delete, and move.

## Key Concepts

- Composite Pattern: Files and folders as tree structure
- Command Pattern: File operations

## Example (Java)

```java
interface FileSystemComponent {
    void show();
}
class File implements FileSystemComponent {
    public void show() { System.out.println("File"); }
}
class Folder implements FileSystemComponent {
    private List<FileSystemComponent> children = new ArrayList<>();
    public void add(FileSystemComponent c) { children.add(c); }
    public void show() {
        for (FileSystemComponent c : children) c.show();
    }
}
```

## When to Use

- Systems with hierarchical data
- File management applications

## Advantages

- Supports recursive structures
- Modular and extensible

## Disadvantages

- Can be complex
- Requires careful management of references

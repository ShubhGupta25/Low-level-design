# Iterator Pattern

## What is it?

A behavioral design pattern that provides a way to access elements of a collection sequentially without exposing its underlying representation.

## When to Use

- Traverse collections without exposing internals
- Support multiple traversals

## How to Use

1. Define an iterator interface
2. Implement concrete iterator classes
3. Collection provides iterator

## Example (Java)

```java
interface Iterator<T> {
    boolean hasNext();
    T next();
}
class MyList<T> {
    private List<T> items = new ArrayList<>();
    public void add(T item) { items.add(item); }
    public Iterator<T> iterator() {
        return new MyListIterator<>(items);
    }
}
class MyListIterator<T> implements Iterator<T> {
    private List<T> items;
    private int index = 0;
    public MyListIterator(List<T> items) { this.items = items; }
    public boolean hasNext() { return index < items.size(); }
    public T next() { return items.get(index++); }
}
```

## Advantages

- Encapsulates traversal logic
- Supports multiple traversals

## Disadvantages

- More classes
- Can be overkill for simple collections

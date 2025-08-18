# Iterator Pattern - Hands-on

## Implementation Example (Java)

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
class Main {
    public static void main(String[] args) {
        MyList<String> list = new MyList<>();
        list.add("A");
        list.add("B");
        Iterator<String> it = list.iterator();
        while (it.hasNext()) {
            System.out.println(it.next());
        }
    }
}
```

## How it works

- Iterator traverses collection

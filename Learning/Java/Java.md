- [[Syntax]]

# Stream API

The **Stream API** in Java is a **powerful tool** introduced in Java 8 that allows you to process **collections of data (like Lists or Sets) in a functional and declarative style** — meaning you can describe _what_ you want done, not _how_ to do it.

## What is a Stream?

A **Stream** is **not** a data structure. It's a **pipeline of operations** you can perform on a data source (like a `List`) to transform, filter, sort, and collect data.

Think of it like a **conveyor belt**:

1. Data comes in.
2. It goes through a series of **steps** (filtering, mapping, etc.).
3. A result comes out (like a list, a count, or a sum).

Example:
```java
List<String> names = List.of("Alice", "Bob", "Charlie", "Anna");

List<String> result = names.stream()
    .filter(name -> name.startsWith("A"))
    .map(String::toUpperCase) // equal to .map(name -> name.toUpperCase())
    .sorted()
    .collect(Collectors.toList());

System.out.println(result); // Output: [ALICE, ANNA]
```

## Key Stream Operations

| Operation   | Description                           |
| ----------- | ------------------------------------- |
| `filter()`  | Keeps elements that match a condition |
| `map()`     | Transforms elements                   |
| `sorted()`  | Sorts the stream                      |
| `collect()` | Gathers the result into a collection  |
| `forEach()` | Performs an action on each element    |
| `reduce()`  | Reduces to a single value (e.g. sum)  |

## Important Notes

- **Streams are single-use** — once consumed, they can’t be reused.
- They can be **sequential or parallel**.
- Streams **don't change the original data source**.
# Overview
Is a design pattern where you **delay the initialization of an object until it’s actually needed**.
- Instead of loading all data immediately, you load it **on-demand**.
- This saves **memory and processing time**, especially if some data might never be used.

**Example (general programming concept):**
```java
class Image {
    private String filePath;
    private byte[] data; // heavy resource

    public byte[] getData() {
        if (data == null) { // load only when needed
            data = loadImageFromDisk(filePath);
        }
        return data;
    }
}
```

Here, the image data is loaded **only when `getData()` is called**, not when the `Image` object is created.

## Analogy:  
Think of lazy loading as a **restaurant menu**. You don’t cook all dishes at once; you only cook **what the customer orders**. Eager loading would be **preparing all dishes before anyone orders**, which can waste resources.

---
# Hibernate[^1]

Hibernate uses lazy loading for **associations and collections**.
- If an entity has a relationship (e.g., `@OneToMany`), Hibernate **doesn’t load the related entities immediately**.
- Instead, it creates a **proxy object**. When you access the collection, Hibernate fetches the data **from the database at that moment**.

**Example:**
```java
@Entity
class User {
    @Id
    private Long id;
    private String name;
	
    @OneToMany(mappedBy = "user", fetch = FetchType.LAZY)
    private List<Order> orders;
}

// Using Hibernate
User user = entityManager.find(User.class, 1L);
// At this point, 'orders' are NOT loaded yet
List<Order> orders = user.getOrders(); // Lazy loading triggers here
```

**Key points:**

- Default behavior for `@OneToMany` and `@ManyToMany` is `LAZY`.
- Default behavior for `@ManyToOne` and `@OneToOne` is `EAGER` (but can be overridden to LAZY).
- **Pros:** Reduces unnecessary DB queries and memory usage.
- **Cons:** Can cause `LazyInitializationException` if you try to access the data **outside of an active session**.


[^1]: [[JPA & Hibernate]]

# Overview
**ORM** stands for **Object-Relational Mapping**.

In the context of **JPA (Jakarta Persistence API)**:
- **Java objects (entities)** represent your database tables.
- **Fields in those objects** represent the table columns.
- The ORM framework (like **Hibernate**[^1], which is the most popular JPA implementation) automatically **translates between objects and database records**.
- As I say in [[JPA & Hibernate]], to me is more easy to understand comparing ORM as a compiler from Java to SQL.

Example:
```java
@Entity
@Table(name = "users")
public class User {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    private String name;
    private String email;
}
```

Here:

- The class `User` is mapped to the table `users`.
- The attributes `name` and `email` are mapped to columns in that table.
- When you call `entityManager.persist(user)`, JPA uses ORM to convert the **object** into an **INSERT SQL statement** automatically.

So instead of writing SQL like:
```sql
INSERT INTO users (name, email) VALUES ('Alice', 'alice@email.com');
```

You just work with Java objects, and the ORM layer handles the persistence logic.

# TL;DR:  
**ORM in JPA is the mechanism that maps Java objects to database tables and handles converting between them, so you don’t have to write most SQL manually.**

[^1]: [[JPA & Hibernate]]

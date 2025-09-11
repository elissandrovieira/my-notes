# Overview
## JPA (Java Persistence API)

- **Definition:** JPA is a **specification**, not an implementation. It defines a standard way to manage relational data in Java applications.

- **Purpose:** It allows you to map Java objects (like `User`, `Order`, `Product`) to database tables and perform CRUD operations without writing raw SQL.

- **Key concepts:**
    - **Entity:** A Java class mapped to a table (`@Entity` annotation).
    - **Primary Key:** Usually annotated with `@Id`.
    - **Repository/Entity Manager:** Interface to persist, find, delete, and update objects.
    - **JPQL (Java Persistence Query Language):** A query language similar to SQL but works with entities, not tables.

Think of JPA as the **rulebook or blueprint** for how Java apps interact with databases.

---

## Hibernate

- **Definition:** Hibernate is **an implementation of JPA**. It actually does the work behind the scenes: connecting to the database, generating SQL, and executing it.

- **Extra features beyond JPA:**
    - Caching (to improve performance)
    - Lazy loading
    - Advanced mapping strategies
    - Support for some database-specific features


So if JPA is the **rulebook**, Hibernate is a **concrete player following those rules** but also adding some tricks.

---

## Relationship Between Them

|Aspect|JPA|Hibernate|
|---|---|---|
|Type|Specification/Interface|Implementation/Library|
|Purpose|Standardize ORM in Java|Provide ORM functionality|
|Requires|A JPA provider (like Hibernate)|Nothing else, it can implement JPA|
|Extra features|No extra features|Yes, many optimizations|

---

## Example in code (simplified)

```java
@Entity
public class User {
    @Id
    @GeneratedValue
    private Long id;

    private String name;
    private String email;
}
```

```java
// Using JPA EntityManager
EntityManager em = ...;
em.persist(new User("Elissandro", "elissandro@email.com"));
```

Here, JPA defines `@Entity`, `@Id`, `EntityManager`, etc. Hibernate is the library that actually talks to the database when you call `persist`.
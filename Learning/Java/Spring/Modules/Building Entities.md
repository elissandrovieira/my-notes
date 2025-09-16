Entities are model classes for Database. To turn models in entities, we need a Spring dependency called  `Spring Data JPA`,[^1] and we can use the `@Entity` annotation.

```java
@Entity
public class User {  
```
# Attributes
Entities need to have attributes like models. Attributes that define the data stored for this specific object. But in addition to all attributes that we want add into a model, in entities we should add a id attribute.

This attribute shouldn't be in constructors, getters and setters. It is "automatically generated" to store in DB.

# Constructors
Is a good choice generate no and all args constructors in addition to getters and setters.

```java
public class User {  
  
    private Long id;  
    private String name;  
    private String email;  
    private String passwordHash;  
  
    public User() //No args constructor
    
    public User(Long id, String name, String email, String passwordHash) {  
        this.id = id;  
        this.name = name;  
        this.email = email;  
        this.passwordHash = passwordHash;  
    } //Full args constructor
}
```

[^1]: [[JPA & Hibernate]]

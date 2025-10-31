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

So here bellow I paste my code and explain each thing, I'm using a Vault entity as example:

```java
package com.zetteln.backend.entity;  
  
import jakarta.persistence.*; //JPA(Java/Jakarta Persistence API)
//Lombok is a dependency to reduce boilerplate like constructors, getters and setters
import lombok.AllArgsConstructor;  
import lombok.Data;  
import lombok.NoArgsConstructor;  
  
import java.util.List;  
  
@Entity //Declare model as an entity
@Table(name = "tb_vaults") //Declare the table name
@NoArgsConstructor
@AllArgsConstructor  
@Data //Declare Getters & Setters
public class Vault {  
  
    @Id //Generate Id
    @GeneratedValue(strategy = GenerationType.IDENTITY) //Choose the strategy generation type
    private Long id;  
  
    @ManyToOne //Many current entity(Vault) to one entity bellow(User)
    @JoinColumn(name = "user_id") //Choose the colunm table to relate as a foreing key
    private User user;   
  
    private String name;  
  
    @OneToMany
		mappedBy = "vault",
		cascade = CascadeType.ALL,
		orphanRemoval = true
	) //One current entity(Vault) to one entity bellow(Note)
    private List<Note> notes;  
}
```

[^1]: [[JPA & Hibernate]]

The repository is a package in the project for  DAO (DAO — _Data Access Object_) interfaces, while the repositories themselves (like `UserRepository`) are the ones that extend `JpaRepository`[^1] and provide data access methods.

Example:
```java
package com.zetteln.backend.repository;  
  
import com.zetteln.backend.entity.Vault;  
import org.springframework.data.jpa.repository.JpaRepository;  

//<Entity Name, Id Type>
public interface VaultRepository extends JpaRepository<Vault, Long> {  
}
```



[^1]: **JpaRepository:**  Is a interface from JPA([[JPA & Hibernate]]) that help us to build queries in a more easy way.

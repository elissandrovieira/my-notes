# Spring Boot convention

In Spring Boot, we usually **split into layers** (controller → service → repository → entity) because:

- It’s opinionated and helps scale backend APIs.
- Spring auto-detects beans by package scanning.
- Separation of concerns is more formal (e.g., DTOs vs Entities).

---
## 📂 Project Structure

``` bash
src/
 └── main/
      ├── java/
      │    └── com/example/projectname/
      │         ├── config/          # Spring and security configs (CORS, JWT, etc.)
      │         ├── controller/      # REST controllers (entry points)
      │         ├── dto/             # Data Transfer Objects (request/response payloads)
      │         ├── entity/          # JPA entities (database tables mapping)
      │         ├── exception/       # Custom exceptions & handlers
      │         ├── repository/      # Data access layer (Spring Data JPA)
      │         ├── service/         # Business logic layer
      │         ├── util/            # Utility classes/helpers
      │         └── ProjectNameApplication.java  # Main Spring Boot app
      │
      └── resources/
           ├── application.yml       # Main configuration (profiles, DB, etc.)
           ├── static/               # Static files (if serving any assets)
           └── templates/            # Thymeleaf or Freemarker (if used)

```

---
## 📖 Layer Responsibilities

- **config/**  
	- Where you keep global Spring configs:
	    - SecurityConfig, WebMvcConfig, SwaggerConfig, etc. 
	
- **controller/**
    - REST endpoints (`@RestController`)
    - They don’t hold business logic, just handle request/response mapping.
    
- **dto/**
    - Classes that represent payloads sent/received in API.
    - Keeps controllers decoupled from entities (good for versioning + security).
    
- **entity/**
    - JPA entity classes mapped to DB tables with `@Entity`.
    
- **exception/**
    - Centralized exception handling (`@ControllerAdvice`).
    - Custom exceptions like `ResourceNotFoundException`.
    
- **repository/**
    - Interfaces extending `JpaRepository` (DAO layer).
    - Example: `UserRepository extends JpaRepository<User, Long>`.
    
- **service/**
    - Business logic lives here.
    - Services call repositories and return DTOs/entities to controllers.
    
- **util/**
    - Utility classes, constants, validators, converters, etc.

---

## 📌 Example Flow

👉 `UserController` → receives HTTP request  
👉 calls `UserService` → applies business logic  
👉 calls `UserRepository` → fetches from DB  
👉 returns DTO → mapped into HTTP response

---

## ✅ Example Package with Files

``` sql
com.example.projectname
 ├── config
 │     └── SecurityConfig.java
 ├── controller
 │     └── UserController.java
 ├── dto
 │     └── UserRequest.java
 │     └── UserResponse.java
 ├── entity
 │     └── User.java
 ├── exception
 │     └── GlobalExceptionHandler.java
 │     └── ResourceNotFoundException.java
 ├── repository
 │     └── UserRepository.java
 ├── service
 │     └── UserService.java
 │     └── impl/UserServiceImpl.java
 └── util
       └── MapperUtil.java

```
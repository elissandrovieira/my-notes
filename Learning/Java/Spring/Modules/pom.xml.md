`pom.xml` = Project Object Model (POM) file.
It is the heart of your [[Maven]] project. It tells how to build, manage and package your application.

Is like a `package.json` in a Node.js project.
It’s where you declare:

- Project metadata (name, version, description)
- Dependencies (like Spring Boot, JPA, Lombok, etc.)
- Plugins (for building, testing, packaging)
- Build profiles (dev, test, prod)
- Java version

---

## Example `pom.xml` for Spring Boot

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0
                             http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <!-- Project coordinates -->
    <groupId>com.example</groupId>
    <artifactId>demo</artifactId>
    <version>1.0.0</version>
    <packaging>jar</packaging>

    <!-- Parent Spring Boot BOM (Bill of Materials) -->
    <parent>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-parent</artifactId>
        <version>3.3.2</version>
    </parent>

    <!-- Project properties -->
    <properties>
        <java.version>17</java.version>
    </properties>

    <!-- Dependencies -->
    <dependencies>
        <!-- Web API -->
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-web</artifactId>
        </dependency>

        <!-- Database (JPA + H2 for dev) -->
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-data-jpa</artifactId>
        </dependency>
        <dependency>
            <groupId>com.h2database</groupId>
            <artifactId>h2</artifactId>
            <scope>runtime</scope>
        </dependency>

        <!-- Lombok (optional for reducing boilerplate) -->
        <dependency>
            <groupId>org.projectlombok</groupId>
            <artifactId>lombok</artifactId>
            <optional>true</optional>
        </dependency>

        <!-- Testing -->
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-test</artifactId>
            <scope>test</scope>
        </dependency>
    </dependencies>

    <!-- Build configuration -->
    <build>
        <plugins>
            <!-- Spring Boot plugin -->
            <plugin>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-maven-plugin</artifactId>
            </plugin>
        </plugins>
    </build>
</project>

```

---
## What happens with it?

- When you run `mvn clean install` or `mvn spring-boot:run`, Maven looks at your `pom.xml`, downloads the dependencies from **Maven Central** (like npm downloads from registry), and builds your project.
- Dependencies are **transitive**: if you add Spring Boot Starter Web, Maven also downloads Tomcat, Jackson, Validation, etc.

---

👉 In short:  
`pom.xml` is your **project manifest** + **dependency manager** + **build config** for Maven.

---
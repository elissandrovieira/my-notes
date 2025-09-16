## 1. **Spring Boot Starter Web Dependency**

When you add
```xml
<dependency>
  <groupId>org.springframework.boot</groupId>
  <artifactId>spring-boot-starter-web</artifactId>
</dependency>

```

to your `pom.xml`, you’re basically saying:
> "I want to build a web application (REST API or traditional web app) with Spring Boot."

That **starter** is a _convenience dependency_. Instead of you manually adding dozens of libraries (like Jackson for JSON, validation, Spring MVC, Tomcat, logging, etc.), the **starter pulls them all in** for you automatically.

By default, `spring-boot-starter-web` includes things like:
- **Spring MVC** → the web framework (controllers, routes, request mapping, etc.)
- **Jackson** → JSON (object ↔ JSON conversion)
- **Validation API** → Bean validation (like `@Valid`)
- **Embedded Tomcat** → the default server that runs your app (unless you choose Jetty or Undertow)

So the starter gives you everything you need to run a web server out-of-the-box.

---

### 2. **Tomcat**

Tomcat is a **web server and [[Servlet Container]]**.
- A **web server** handles HTTP requests (like when a browser or `curl` makes a request).
- A **servlet container** runs _Java servlets_, which are Java classes that handle requests and responses.

Think of it like this:
- Your **Spring controllers** (annotated with `@RestController`, `@GetMapping`, etc.) are essentially specialized _servlets_.
- Tomcat is the engine that takes an incoming HTTP request (`GET /users`), finds the right servlet (your controller method), runs it, and sends back an HTTP response.

In traditional Java EE (Jakarta EE) development, you had to deploy your app (`.war` file) into an external Tomcat server[^1].

But with **Spring Boot**, Tomcat is **embedded** by default. That’s why you can just run:
```zsh
mvn spring-boot:run
```

and immediately visit `http://localhost:8080` — Tomcat is already bundled inside your app’s JAR.

---

## TL;DR:

- **spring-boot-starter-web**: a package of all dependencies to quickly build web apps with Spring Boot.
- **Tomcat**: the default embedded server that runs your Spring web app and handles HTTP requests/responses.

[^1]: # 🐒 Explanation for Monkeys:
	**Traditional Java EE way:**	
	1. You write your web app (just servlets, JSPs, etc.).
	2. You package it into a **`.war` file** (Web Application Archive = basically a zip with your code + config).
	3. You take that `.war` file and **throw it into a Tomcat server** that’s already installed on your machine or on a company server.
	    - Tomcat = the “big house” 🏠.
	    - Your `.war` = a “guest” that moves into the house.
	4. Tomcat opens the `.war`, loads it, and makes it run on some port (like 8080).
	So you always needed **an external Tomcat running first**, and then you dropped your app into it.
	
	**Spring Boot way:**
	- Spring Boot **bundles Tomcat inside your app**.
	- Instead of creating a `.war` and putting it into Tomcat’s house, you package everything into a **fat `.jar` file**.
	- That `.jar` already has your app **+ Tomcat inside it**.
	- You just run:
	```zsh
	java -jar myapp.jar
	```
	- and BOOM 💥, Tomcat starts automatically, your app is alive at `localhost:8080`.
	So now, your app **carries its own house** on its back 🐢. No need to find an external Tomcat house.
	
	**Monkey analogy:**
	- **Traditional EE** = 🐒 builds a banana cart (`.war`) and must bring it to the big zoo (`Tomcat server`) so people can eat bananas.
	- **Spring Boot** = 🐒 builds a banana cart **with a mini-zoo inside**. Wherever the cart goes, the zoo goes too. People can eat bananas right away. 🍌🎉

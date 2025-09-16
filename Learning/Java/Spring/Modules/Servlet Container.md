## **Servlet Container (a.k.a. Web Container)**

A **servlet container** is a piece of software (like Tomcat, Jetty, or Undertow) that:

1. **Listens for HTTP requests** (like `GET /users`) on some port (e.g., `8080`).
2. **Creates servlet objects** (your web components, e.g., controllers in Spring) and manages their lifecycle.
3. **Passes the request** into the right servlet method.
4. **Collects the response** from that servlet and sends it back to the client (browser, Postman, curl, etc.).

---

## **Why is it called "servlet" container?**

- A **servlet** is just a Java class that follows the _Servlet API_ (it extends `HttpServlet` or uses annotations).
- It has methods like:
    - `doGet()` → runs when an HTTP GET request arrives.
    - `doPost()` → runs when an HTTP POST request arrives.
- The **servlet container** is the runtime environment that executes those servlets.

---

## **Responsibilities of a Servlet Container**

- **Lifecycle management** → it creates, initializes, and destroys servlets.
- **Routing** → decides which servlet should handle each request (like a little traffic cop).
- **Security** → handles authentication, SSL, etc.
- **Concurrency** → runs many requests in parallel using threads.
- **Integration** → provides APIs for cookies, sessions, filters, etc.

---

## Analogy

Think of a servlet container like an **airport terminal**:

- The **terminal (container)** manages everything: gates, check-in, luggage, schedules.
- **Planes (servlets)** are what actually carry people (process requests).
- Passengers (HTTP requests) arrive at the terminal, the terminal decides which plane (servlet) they should board, and then the plane takes them to their destination (response).

Without the terminal (servlet container), planes (servlets) couldn’t operate efficiently — they wouldn’t know where to go, when to fly, or how to get passengers.

---

**TL;DR:**  

A **servlet container** is a runtime inside the server that:

- Knows how to handle **HTTP requests/responses**.
- Provides the **structure and lifecycle management** for servlets (Java web components).
- Lets you focus on writing logic, while it takes care of the low-level plumbing (threads, routing, sessions, etc.).

That’s why Spring Boot doesn’t reinvent the wheel — it just uses an embedded servlet container (Tomcat by default) to do all that work for you.

---
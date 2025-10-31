When an application grows, the database schema (tables, columns, relationships) also evolves. For example, you might start with a `users` table, but later need to add an `email` column or create an `orders` table.

If you just run SQL scripts manually, it becomes hard to:
- Track which changes have been applied in each environment (dev, test, prod).
- Ensure every team member is working with the same database version.
- Roll back if something goes wrong.

**Database migrations** solve this problem by treating schema changes like **versioned code**. Each change is stored in a migration file with a unique identifier. Tools then apply these migrations in the correct order, keeping the database consistent everywhere.

---

## Liquibase

Liquibase is a migration tool that:
- Lets you describe schema changes in **changelogs** (XML, YAML, JSON, or SQL).
- Tracks which changes have already been applied using a special table in the database.
- Provides rollback support and advanced features (diff, audit, etc.).

👉 Example (YAML changelog):
```yaml
databaseChangeLog:
  - changeSet:
      id: 1
      author: dev
      changes:
        - addColumn:
            tableName: users
            columns:
              - column:
                  name: email
                  type: varchar(150)

```

---
## Flyway

Flyway is another migration tool, but simpler and more lightweight.

- It usually works with **SQL scripts** named with version numbers (e.g., `V1__create_users.sql`, `V2__add_email.sql`).
- Each script is applied in order, and Flyway also keeps track of what has been executed.
- Very popular in Spring Boot projects because of its simplicity and out-of-the-box integration.

👉 Example (SQL migration file `V2__add_email.sql`):
```sql
ALTER TABLE users ADD COLUMN email VARCHAR(150);
```

---

## TL;DR

- **Migrations** are the process of version-controlling database schema changes.
- **Liquibase** and **Flyway** are two popular tools that automate migrations, ensuring your database schema evolves safely and consistently along with your application code.
- Liquibase = more flexible, supports multiple formats.
- Flyway = simpler, mostly SQL-based, common in Spring Boot.
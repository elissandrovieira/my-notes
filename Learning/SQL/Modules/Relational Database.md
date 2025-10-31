A **relational database (RDB)** is a type of database that stores data in **tables** (also called relations). Each table is made of:

- **Rows (records)** → represent individual data entries.
- **Columns (fields)** → represent the attributes of that data.

The power of relational databases comes from the **relationships** between tables. Instead of putting all information in one big table, you split data into multiple tables and connect them with **keys**:

- **Primary Key (PK):** a unique identifier for each row in a table.
- **Foreign Key (FK):** a reference to a primary key in another table, used to create a relationship.

👉 Example:

**Table: Users**

| id (PK) | name  | email                                     |
| ------- | ----- | ----------------------------------------- |
| 1       | Alice | [alice@email.com](mailto:alice@email.com) |
| 2       | Bob   | [bob@email.com](mailto:bob@email.com)     |

**Table: Orders**

|id (PK)|user_id (FK)|product|
|---|---|---|
|1|1|Laptop|
|2|2|Keyboard|
|3|1|Mouse|

Here:
- `Users.id` is the **primary key**.
- `Orders.user_id` is a **foreign key** pointing to `Users.id`.
- This means each order belongs to a user.

So if we ask: _“What did Alice order?”_  
We join the two tables with SQL:
```sql
SELECT u.name, o.product
FROM Users u
JOIN Orders o ON u.id = o.user_id
WHERE u.name = 'Alice';
```

Result:
- Alice → Laptop
- Alice → Mouse

---

**TL;DR:**  
Relational databases organize data into tables and use **relationships** (through keys) to connect them. This makes data consistent, avoids duplication, and lets you query complex information with SQL.
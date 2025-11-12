# 🧠 **Kalvium AL 1.10 — Introduction to Databases: Relational (SQL) vs. Non-Relational (NoSQL)**

Fully structured, logically ordered, and explained with **technical precision** for study and exam reference.

---

## **1. Introduction**

### **Definition**

A **database** is an organized collection of data that can be easily accessed, managed, and updated.  
Every modern application — social media, e-commerce, finance — depends on databases to store and retrieve data efficiently.

### **Core Purpose**

- Store and organize data.
- Ensure data integrity, security, and consistency.
- Enable querying, updating, and analysis.

There are **two main categories**:

1. **Relational Databases (SQL)**
2. **Non-Relational Databases (NoSQL)**

---

## **2. The Two Database Worlds**

|Type|Description|
|---|---|
|**SQL (Structured Query Language)**|Data stored in **tables** (rows and columns) with predefined relationships.|
|**NoSQL (Not Only SQL)**|Data stored in **flexible formats** such as documents, key-value pairs, or graphs.|

> ⚙️ Neither is "better" — the choice depends on your **data structure, scalability needs, and consistency requirements.**

---

## **3. SQL Databases (Relational Model)**

### **3.1. Structure**

- Data organized into **tables** (like Excel sheets).
- Each table has:
    - **Rows** → Individual records.
    - **Columns** → Fields (attributes).
- Tables are linked through **relationships** (foreign keys).

**Example:**

**Users Table**

|id|username|email|age|
|---|---|---|---|
|1|alice|alice@email.com|25|
|2|bob|bob@email.com|30|

**Posts Table**

|id|user_id|content|
|---|---|---|
|1|1|Hello World!|
|2|2|SQL is awesome|

🔗 The `user_id` in `Posts` links to `id` in `Users` — this is a **foreign key relationship**.

---

### **3.2. Schema-on-Write (Structure First)**

SQL databases require a predefined structure called a **schema** before storing data.

```sql
CREATE TABLE users (
  id INT PRIMARY KEY,
  username VARCHAR(50) NOT NULL,
  email VARCHAR(100) NOT NULL,
  age INT
);

```

**Key Characteristics**

- Structure **must** be defined before inserting data.
- Database enforces **data rules**:
    - Mandatory fields (`NOT NULL`)
    - Data types (`INT`, `VARCHAR`, etc.)
    - Constraints (e.g., `PRIMARY KEY`, `FOREIGN KEY`)

**Advantages**  
✅ Strong data consistency  
✅ Clear data structure  
✅ Easier data validation and integrity enforcement

---

### **3.3. When to Use SQL**

- Banking / Financial systems (e.g., transactions)
- E-commerce (products, orders, customers)
- Applications with **complex relationships**
- Data that rarely changes structure
- Systems needing **ACID** guarantees

**ACID** → Atomicity, Consistency, Isolation, Durability  
→ Ensures **perfect accuracy and reliability** in transactions.

---

### **3.4. Popular SQL Databases**

- **PostgreSQL**
- **MySQL**
- **SQLite**
- **Microsoft SQL Server**
- **Oracle Database**

---

## **4. NoSQL Databases (Non-Relational Model)**

### **4.1. Structure**

NoSQL databases do **not** rely on tables.  
They store data in **flexible formats** depending on the type of database.

### **Main Types**

|Type|Description|Example|
|---|---|---|
|**Document-Based**|Stores data as JSON-like objects.|MongoDB|
|**Key-Value Store**|Data stored as key-value pairs.|Redis|
|**Column-Family Store**|Data grouped in columns, optimized for queries.|Cassandra|
|**Graph Database**|Stores entities and their relationships.|Neo4j|

---

### **4.2. Document Database Example (MongoDB)**

```js
{
  "_id": "user123",
  "username": "alice",
  "email": "alice@email.com",
  "posts": [
    {
      "title": "Hello World",
      "likes": 42,
      "comments": [
        {"user": "bob", "text": "Great post!"}
      ]
    }
  ]
}


```

➡ Everything related to a user is stored in one **document**, not spread across multiple tables.

---

### **4.3. Key-Value Store Example (Redis)**

```json
"user:123" → {"name": "Alice", "email": "alice@email.com"}
"session:abc" → {"userId": 123, "expires": 1234567890}

```
➡ Extremely fast lookups using keys.

---

### **4.4. Graph Database Example (Neo4j)**

```SCSS
(Alice)-[:FOLLOWS]->(Bob)
(Alice)-[:LIKES]->(Post123)
```
➡ Perfect for **social networks**, where relationships are core.

---

### **4.5. Schema-on-Read (Flexible Structure)**

- No schema required before data insertion.
- Structure defined **when data is read**.
- Each document can have different fields.

**Example:**

```json 
// User 1
{"username": "alice", "email": "alice@email.com"}

// User 2
{"username": "bob", "age": 30, "premium": true}

```

Both valid — no enforced schema.

---

### **4.6. When to Use NoSQL**

- **Social media apps** (flexible post formats)
- **Chat / Gaming / Real-time** apps
- **Analytics / IoT** (rapidly changing data)
- **Massive scalability** requirements
- **Rapid prototyping** or frequently evolving projects

---

### **4.7. Popular NoSQL Databases**

- **MongoDB** → Document storage
- **Redis** → Caching & fast key-value operations
- **Cassandra** → High scalability, column-based
- **DynamoDB** → AWS managed NoSQL
- **Neo4j** → Relationship-based graph database

---

## **5. SQL vs. NoSQL — Head-to-Head Comparison**

|Aspect|**SQL**|**NoSQL**|
|---|---|---|
|**Data Structure**|Tables (rows, columns)|Documents, key-value, graphs, etc.|
|**Schema Type**|Schema-on-Write (predefined)|Schema-on-Read (flexible)|
|**Scalability**|Vertical (bigger servers)|Horizontal (add more servers)|
|**Best For**|Complex relationships, transactions|Flexibility, evolving structures|
|**Consistency**|Strong (ACID compliant)|Eventual consistency|
|**Performance**|Optimized for joins and structured queries|Optimized for fast reads/writes|
|**Examples**|MySQL, PostgreSQL, SQLite|MongoDB, Redis, Cassandra|

---

## **6. Scaling Concepts**

### **6.1. Vertical Scaling (SQL)**

- Add more power (CPU/RAM) to a single server.
- Works until hardware limits are reached.

|Time|Server Size|Users Supported|
|---|---|---|
|Day 1|Small|1,000|
|Day 30|Medium|10,000|
|Day 90|Big|50,000|
|Day 150|Huge|100,000|
|→ Limit reached|⚠️ Cannot scale further easily||

---

### **6.2. Horizontal Scaling (NoSQL)**

- Add more servers (distributed system).
- Theoretically unlimited growth.

|Time|Servers|Users Supported|
|---|---|---|
|Day 1|1|10,000|
|Day 30|3|30,000|
|Day 90|10|100,000|
|Day 200|100|1,000,000|

> 💡 **Trade-off:** You may lose strict consistency, but gain massive scalability.

---

## **7. Choosing Between SQL and NoSQL**

### **Choose SQL When**

- Data is **structured** and rarely changes.
- Relationships between entities are complex.
- You need **transactions and accuracy**.
- Example: Banking, e-commerce, inventory.

### **Choose NoSQL When**

- Data is **unstructured or semi-structured**.
- Schema or data model changes frequently.
- Application requires **high scalability** and **speed**.
- Example: Social media, chats, analytics, IoT.

```embed
title: "SQL vs. NoSQL Explained (in 4 Minutes)"
image: "https://i.ytimg.com/vi/_Ss42Vb1SU4/maxresdefault.jpg"
description: "Make sure you're interview-ready with Exponent's system design interview prep course: https://bit.ly/3P2tvByGet our database cheatsheet: https://www.tryexpon..."
url: "https://youtu.be/_Ss42Vb1SU4"
favicon: ""
aspectRatio: "56.25"
```

---

## **8. Real-World Examples**

|Application Type|Best Database|Reason|
|---|---|---|
|Banking App|SQL (PostgreSQL)|Accurate, ACID transactions|
|Instagram|NoSQL (Cassandra)|Billions of posts, flexible formats|
|E-commerce|SQL (MySQL)|Orders, products, relationships|
|Chat App|NoSQL (MongoDB)|Real-time, dynamic message structures|
|Analytics|SQL (PostgreSQL)|Complex data queries and aggregation|
|Gaming Leaderboards|NoSQL (Redis)|High-speed reads/writes|

---

## **9. Schema Trade-Off Summary**

|Concept|SQL (Schema-on-Write)|NoSQL (Schema-on-Read)|
|---|---|---|
|Define structure|Before data entry|At data retrieval|
|Validation|Database enforced|Application enforced|
|Flexibility|Rigid|Highly flexible|
|Data safety|High|Depends on app logic|
|Changes|Requires migration|Instantly adaptable|

---

## **10. Key Takeaways**

- **SQL =** Structured, relational, rule-driven, ideal for **accuracy and relationships**.
- **NoSQL =** Flexible, scalable, schema-free, ideal for **speed and evolving data**.
- **Schema-on-Write (SQL)** → Structure first, then data.
- **Schema-on-Read (NoSQL)** → Store data first, interpret later.
- **Vertical scaling (SQL)** → Bigger machines.
- **Horizontal scaling (NoSQL)** → More machines.
- Modern systems often use **both** (polyglot persistence).
    

> Example:  
> Netflix uses **Cassandra (NoSQL)** for streaming data  
> and **PostgreSQL (SQL)** for billing and transactions.

---

## **11. Exam-Focused Quick Summary**

|Topic|SQL|NoSQL|
|---|---|---|
|Structure|Tables|Documents / Key-Value|
|Schema|Fixed|Flexible|
|Scaling|Vertical|Horizontal|
|Query Language|SQL|Varies (JSON, APIs)|
|Consistency|Strong (ACID)|Eventual|
|Performance|Moderate|High at scale|
|Use Cases|Banking, inventory|Social apps, chat|
|Examples|MySQL, PostgreSQL|MongoDB, Redis|
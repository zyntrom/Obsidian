## 📘 **1. Introduction to NoSQL Database Models**

### 1.1 Purpose of NoSQL Models

- Traditional **SQL databases** (tables, rows, columns) can’t efficiently handle modern large-scale, high-speed, or unstructured data.
- **NoSQL databases** were developed to provide **specialized solutions** based on data patterns and performance requirements.
- Each NoSQL model is optimized for **different workloads** — flexibility, speed, scalability, or relationships.

### 1.2 The Four Major NoSQL Models

|Model|Example|Key Strength|Ideal Use Case|
|---|---|---|---|
|**Document**|MongoDB|Flexible, JSON-like data|User profiles, catalogs|
|**Key-Value**|Redis|Ultra-fast lookup speed|Caching, sessions|
|**Column-Family**|Cassandra|High write performance|IoT, time-series|
|**Graph**|Neo4j|Relationship-based queries|Social networks, recommendations|

---

## 📗 **2. Document Databases**

### 2.1 Core Concept

- Store data as **JSON-like documents** (key–value pairs, nested objects, arrays).
- Each record (document) can have a **different structure** — schema-free design.
- Data is stored in **collections** instead of tables.

### 2.2 Example (MongoDB)

```json
{
  "_id": "user123",
  "name": "Priya Sharma",
  "email": "priya@example.com",
  "addresses": [
    { "type": "home", "city": "Mumbai" },
    { "type": "work", "city": "Bangalore" }
  ],
  "premium": true,
  "lastLogin": "2025-10-20"
}

```

- Fields like `addresses` can vary per document.
- No strict schema → easier for evolving apps.

### 2.3 Advantages

- Flexible schema structure.
- Easy horizontal scaling.
- Ideal for hierarchical data (nested objects).
- Supports rich queries and indexing on fields.

### 2.4 Common Use Cases

- E-commerce product catalogs (different attributes).
- CMS/blogs (varied article metadata).
- User profiles.
- Mobile apps (frequent schema changes).

### 2.5 Real Example

**Forbes CMS** uses MongoDB for flexible article storage across multiple categories.

---

## 📙 **3. Key-Value Databases**

### 3.1 Core Concept

- Simplest NoSQL model.
- Data stored as **key → value** pairs.
- Values can be strings, JSON, or binary data.
- Focused purely on **speed and simplicity**.

### 3.2 Example (Redis)

|Key|Value|
|---|---|
|`"user:123:cart"`|`["item_456", "item_789"]`|
|`"session:xyz"`|`{ "userId": 123, "expires": 1698765432 }`|
|`"page:home:cache"`|`"<html>...</html>"`|

### 3.3 Characteristics

- Extremely fast (in-memory data store).
- Simple get/set operations.
- No querying across keys (each key is independent).
- Ideal for **temporary or rapidly changing data**.

### 3.4 Common Use Cases

- Caching frequently accessed data.
- Session storage for logged-in users.
- Leaderboards in gaming.
- Real-time analytics (counting metrics).

### 3.5 Real Example

**Twitter** uses Redis to cache home timelines, reducing database load for 400M+ users.

---

## 📒 **4. Column-Family Databases**

### 4.1 Core Concept

- Data stored in **rows and columns**, but with flexible column families.
- Optimized for **high write throughput** across distributed systems.
- Each row can contain **millions of columns** with different keys.

### 4.2 Example (Cassandra)

```pgsql
Row Key: sensor_001
 ├─ timestamp:1698765400 → temp:22.5, humidity:65
 ├─ timestamp:1698765401 → temp:22.6, humidity:64
 ├─ timestamp:1698765402 → temp:22.7, humidity:63
```

- Each row key stores time-series column data.
- Excellent for continuous data ingestion.

### 4.3 Advantages

- Scales horizontally (add servers easily).
- Optimized for **high write volumes**.
- Distributed architecture (no single point of failure).
- Tunable consistency (trade-off between speed and accuracy).

### 4.4 Common Use Cases

- IoT device data.
- Server metrics/time-series data.
- Messaging logs and chat history.
- Event tracking.

### 4.5 Real Example

**Netflix** uses Cassandra to handle 1+ trillion writes/day — storing user playback events instantly.

---

## 📕 **5. Graph Databases**

### 5.1 Core Concept

- Designed for **data with complex relationships**.
- Data represented as:
    - **Nodes** → entities (users, posts, products)
    - **Edges** → relationships (friends, likes, follows)
    - **Properties** → attributes of nodes/edges

### 5.2 Example (Neo4j)

```SCSS
(Priya)-[:FRIENDS_WITH]->(Rahul)
(Rahul)-[:WORKS_AT]->(Kalvium)
(Priya)-[:LIKES]->(MongoDB_Course)
(Rahul)-[:LIKES]->(MongoDB_Course)
```

Query example:

> Find all friends of friends who work at “Kalvium”.

### 5.3 Advantages

- Efficient for multi-level relationship queries.
- No complex JOINs (relationships are first-class citizens).
- Real-time relationship discovery.
### 5.4 Common Use Cases

- Social networks.
- Recommendation engines.
- Fraud detection.
- Knowledge graphs.

### 5.5 Real Example

**LinkedIn** uses Neo4j-like graph databases for “People You May Know” and career connections.

---

## 📊 **6. Choosing the Right NoSQL Model**

### 6.1 Decision Framework

|Requirement|Recommended Database|Example|
|---|---|---|
|Frequently changing schema|**Document**|MongoDB|
|Fast lookups and cache|**Key-Value**|Redis|
|High write load and scalability|**Column-Family**|Cassandra|
|Complex relationships|**Graph**|Neo4j|

---

## 🧠 **7. Real-World Scenario Matching**

|Scenario|Best Choice|Reason|
|---|---|---|
|E-commerce catalog|Document (MongoDB)|Different attributes per product|
|Gaming leaderboard|Key-Value (Redis)|Fast read/write with sorted sets|
|Smart city IoT sensors|Column-Family (Cassandra)|Continuous write-heavy data|
|Job referral platform|Graph (Neo4j)|Multi-hop relationship queries|

---

## 🧩 **8. Key Takeaways**

- NoSQL = _Not One Database Fits All_ — each model specializes in a different strength.
- **Document DBs**: Flexible, schema-free JSON structure.
- **Key-Value DBs**: Fastest retrieval for simple data pairs.
- **Column-Family DBs**: Handles massive distributed write loads.
- **Graph DBs**: Best for relationship-heavy datasets.
- The optimal architecture often combines multiple models (polyglot persistence).

---

## 📄 **9. Quick Reference Cheat Sheet**

|Need|Choose|Example|
|---|---|---|
|Flexible nested documents|Document|MongoDB|
|Microsecond-speed lookups|Key-Value|Redis|
|Billions of writes/day|Column-Family|Cassandra|
|Multi-level relationships|Graph|Neo4j|
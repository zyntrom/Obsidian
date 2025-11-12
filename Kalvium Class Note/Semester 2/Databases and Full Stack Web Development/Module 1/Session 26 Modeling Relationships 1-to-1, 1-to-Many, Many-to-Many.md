MongoDB Blog: 6 Rules of Thumb for MongoDB Schema Design Modeling Relationships For this too

###### ChatGPT said:

Here’s a **fully detailed, structured, and explained notes version** for **📘 Kalvium AL 1.26 – Modeling Relationships: 1-to-1, 1-to-Many, Many-to-Many**  
Formatted for clarity, exam revision, and understanding — nothing skipped.

---

# 🧠 **Kalvium 1.26 — Modeling Relationships: 1-to-1, 1-to-Many, Many-to-Many**

---

## 🔹 **Introduction: Connecting the Dots in Data**

- Every database has _entities_ (types of data, e.g., User, Post, Group) and _relationships_ between them.
- These relationships define **how data items are connected** — just like relationships in the real world.

### 🧩 **Schema Definition**

- **Schema** = Blueprint or structure of the database.
- Defines:
    - Collections (like folders for data, e.g., Users)
    - Documents (individual records, e.g., one user’s file)
- In **NoSQL (MongoDB)**, schema = structure of JSON-like documents.

### 💡 Analogy:

Just like people are connected through relationships, data points are connected in a database.

---

## 🧠 **Why Relationships Matter**

- No piece of data exists alone.
    - Blog post → has an author
    - Order → contains products
    - Student → enrolls in courses
- Modeling these links correctly determines performance, scalability, and data integrity.

---

## 🔍 **The Inquiry: Social Media App Example**

We’ll discover relationships using **3 questions**:

|Question|Entities Involved|Relationship Type|Explanation|
|---|---|---|---|
|Users & Profiles|User ↔ Profile|**1-to-1**|One user → One profile|
|Users & Posts|User ↔ Posts|**1-to-Many**|One user → Many posts|
|Users & Groups|User ↔ Groups|**Many-to-Many**|Many users can join many groups|
```embed
title: "DBMS 1 to many,many to many,1 to 1 relationships"
image: "https://i.ytimg.com/vi/O1bi5MjqsAc/maxresdefault.jpg"
description: "DBMS 1 to many,many to many,1 to 1 relationships"
url: "https://youtu.be/O1bi5MjqsAc"
favicon: ""
aspectRatio: "56.25"
```

---

## ⚙️ **Component 1: One-to-One (1-to-1) Relationship**

### 📘 Definition:

A **1-to-1 relationship** exists when **one document** in a collection relates to **exactly one document** in another collection.

### 💡 Real-world Analogy:

Person ↔ Passport  
Each person has **only one passport**, and each passport belongs to **only one person**.

### 💾 Example: User ↔ UserProfile

#### User Document (main object — “hot” data)

```json
{
  "_id": "user123",
  "username": "dave",
  "hashed_password": "..."
}

```
#### UserProfile Document (extended — “cold” data)

```json
{
  "_id": "profile456",
  "user_id": "user123",
  "bio": "Loves hiking.",
  "favorite_color": "blue"
}
```
🔗 Connection: `user_id` in `UserProfile` refers to the user.

### ✅ **Why Split Data Like This?**

- Performance optimization:
    - `User` → accessed frequently (every login, API request).
    - `UserProfile` → accessed rarely (only when viewing profile).
- Smaller, faster reads for frequent operations.

---

## ⚙️ **Component 2: One-to-Many (1-to-N) Relationship**

### 📘 Definition:

One document (parent) relates to **many child documents**.

💡 Analogy: Bookshelf ↔ Books  
One bookshelf holds many books, but each book belongs to one bookshelf.

### 💾 Example: Author ↔ Posts

#### Author Document:

```json
{
  "_id": "authorABC",
  "name": "Alice",
  "posts": ["post1", "post2", "post3"]
}
```

#### Post Documents:

```json
{ "_id": "post1", "title": "My First Post" },
{ "_id": "post2", "title": "My Second Post" },
{ "_id": "post3", "title": "My Third Post" }
```
### 🔗 Relationship:

- One Author → Many Posts
- Each Post → One Author

### ⚙️ **How to Model:**

- Parent (Author) stores an **array of child IDs** (`posts`).
- Ideal for moderate “many” counts where you often fetch children from parent.

---

## ⚙️ **Component 3: Many-to-Many (M-to-N) Relationship**

### 📘 Definition:

Many documents in one collection relate to **many documents** in another.

💡 Analogy: Students ↔ Courses
- A student can enroll in multiple courses.
- A course can have multiple students.

```embed
title: "SQL Server Tutorial - One-to-many and many-to-many table relationships"
image: "https://i.ytimg.com/vi/4q-keGvUnag/maxresdefault.jpg?sqp=-oaymwEmCIAKENAF8quKqQMa8AEB-AH-CYACzAWKAgwIABABGGUgZShlMA8=&rs=AOn4CLBDWMXbpBPoPHjNvOwD3ibGv2ar4w"
description: "LinkedIn Learning is the next generation of Lynda.com. Grow your skills by exploring more SQL Server courses today: https://www.linkedin.com/learning/topics/..."
url: "https://youtu.be/4q-keGvUnag"
favicon: ""
aspectRatio: "56.25"
```

### 💾 Example: Students ↔ Courses

#### Student Documents:

```json
{
  "_id": "student1",
  "name": "Bob",
  "courses": ["courseA", "courseC"]
},
{
  "_id": "student2",
  "name": "Charlie",
  "courses": ["courseB", "courseC"]
}
```

#### Course Documents:

```json
{
  "_id": "courseA",
  "name": "History 101",
  "students": ["student1"]
},
{
  "_id": "courseB",
  "name": "Math 202",
  "students": ["student2"]
},
{
  "_id": "courseC",
  "name": "Art 303",
  "students": ["student1", "student2"]
}
```

### 🔗 Relationship:

- Two-way referencing (arrays of IDs in both entities).
- Used when both sides need to quickly know their connections.

---

## ⚙️ **Component 4: Cardinality and Its Impact on Modeling**

### 📘 Definition:

**Cardinality** = The number of relationships between entities.  
It answers the question **“How many?”**

It helps decide whether to:
- **Embed** documents (put inside parent)
- **Reference** documents (link via IDs)

---

### 🧮 **Cardinality Types & Modeling Choices**

|Cardinality Type|Description|Example|Best Modeling Choice|
|---|---|---|---|
|**One-to-Few**|Small, bounded number of related items|A person with a few addresses|✅ **Embed** directly inside parent|
|**One-to-Many**|Potentially hundreds or thousands|Product with many reviews|⚙️ **Reference** (store child IDs in parent)|
|**One-to-Tons**|Unbounded — millions of children|Server generating logs|❌ **Never embed**; use **Parent Referencing** (child stores parent ID)|

### 🧠 Rule of Thumb:

> Small and bounded → Embed  
> Potentially large → Reference

---

## 🧩 **Component 5: Diagramming Relationships**

### 🖋️ **Steps to Create a Relationship Diagram**

1. **Identify Entities**  
    From your workload characterization (e.g., User, Product, Order, Comment)
2. **Draw Boxes**  
    Each entity = one box.
3. **Connect Entities**  
    Draw lines to represent relationships.
4. **Label Relationship Type**  
    Write on each line:
    - “1-to-1”
    - “1-to-Many”
    - “Many-to-Many”

### 💡 Example: Blog App

```json
User (1) ──────> (Many) Post
Post (1) ──────> (Many) Comment
User (Many) <────> (Many) Group
```

Can be drawn in Excalidraw or similar tools.

---

## ✅ **Component 6: Summary & Key Takeaways**

|Concept|Description|
|---|---|
|**Relationships = Connections**|Define how entities are linked.|
|**1-to-1**|Used for splitting heavy data or optimization.|
|**1-to-Many**|Most common relationship (e.g., author → posts).|
|**Many-to-Many**|Bidirectional relationship, both sides reference each other.|
|**Cardinality**|Decides whether to embed or reference data.|
|**Rule of Thumb**|Few → Embed, Many/Tons → Reference.|

---

## 🚫 **Common Mistakes to Avoid**

|Mistake|Better Practice|
|---|---|
|Embedding unbounded data|Use referencing for high cardinality|
|Ignoring relationship directions|Always decide parent vs child clearly|
|Not considering growth|Plan for scalability from start|
|Over-normalizing NoSQL data|Denormalize when it improves performance|

---

## 📘 **References**

- **MongoDB Blog**: _6 Rules of Thumb for Schema Design_
- **MongoDB Docs**: _Modeling Relationships in NoSQL_

---

## 🏁 **Final Recap**

|Relationship Type|Real Example|Schema Approach|Performance Tip|
|---|---|---|---|
|1-to-1|User ↔ Profile|Reference or Embed|Split hot/cold data|
|1-to-Many|Author ↔ Posts|Parent references child IDs|Cache parent reads|
|Many-to-Many|User ↔ Groups|Two-way referencing|Index both arrays|
|Cardinality|“How many?” factor|Guides design choice|Prevent oversized docs|
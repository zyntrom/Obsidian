## 🧠 Problem Solving Using Programming — Lesson 2 Notes

**Lesson Title:** _Algorithm Design with Pseudocode_  
**Module:** Getting Started with Problem Solving

---

### 💡 What is Pseudocode?

**Pseudocode** is a way to describe algorithms in a **simple, language-agnostic** format.  
It’s a **bridge between your logic and real code**.

It uses **plain English** mixed with programming concepts like `INPUT`, `OUTPUT`, `IF`, `WHILE`, etc., without worrying about syntax like `;` or `{}`.

---

### 🔎 Why Pseudocode?

- Helps **visualize logic** clearly before coding
    
- Makes it easier to **communicate algorithms** to others
    
- Encourages **logical thinking** over syntax memorization
    
- Makes the **transition to real code** smoother
    

---

### 🧠 What is Computational Thinking?

Computational thinking is the **foundation** of solving problems using computers. It helps break down big problems into small steps that a computer can understand and execute.

#### 4 Cornerstones of Computational Thinking:

|Concept|What it means|
|---|---|
|**Decomposition**|Break the problem into smaller parts|
|**Pattern Recognition**|Find patterns within or across problems|
|**Abstraction**|Focus only on relevant info, ignore extra details|
|**Algorithms**|Develop step-by-step instructions to solve the problem|

---

### 🧰 Characteristics of Good Pseudocode

|Feature|Description|
|---|---|
|**Clarity**|Use plain and simple English|
|**Sequencing**|Follow the order of operations logically|
|**Indentation**|Indent inside `IF`, `WHILE`, `FOR` for readability|
|**No Syntax Rules**|Avoid programming-specific syntax; focus on logic|
|**Keywords**|Use common terms like `Start`, `End`, `Input`, `Output`, `If`, `While`, etc.|

---

### 🧾 Common Pseudocode Keywords & Meaning:

|Keyword|Meaning|
|---|---|
|`Start`|Begin the algorithm|
|`End`|End of the algorithm|
|`Input`|Get input from user or system|
|`Output`|Display information to user|
|`Process`|Perform a calculation or logic step|
|`If...Then...Else`|Make a decision|
|`While`|Loop while a condition is true|
|`For`|Loop for a fixed number of steps|

---

### 🧪 Algorithm Design Process (Before Writing Code)

#### Step 1️⃣: Crack the Logic

- Analyze the **inputs**, **processing**, and **expected output**
    
- Think through **conditions**, **calculations**, and **loops**
    

#### Step 2️⃣: Write the Pseudocode

- Convert the logic into structured steps using pseudocode
    
- Focus on **clarity**, not coding syntax
    

---

### 🧮 Examples of Pseudocode

---

#### ✅ **Example 1: Area and Perimeter of Circle**

**Goal**: Given the radius, compute and display the area and perimeter  
**Formulas**:

- Area = π × r × r
    
- Perimeter = 2 × π × r
    
- Use π ≈ 3.14
    

**Pseudocode**:

pgsql

CopyEdit

`Start     Input radius     Set π to 3.14     Compute area = π × radius × radius     Compute perimeter = 2 × π × radius     Output "Area of the circle is: ", area     Output "Perimeter of the circle is: ", perimeter End`

---

#### ✅ **Example 2: Check Voting Eligibility**

**Goal**: Determine if a user is eligible to vote (Age ≥ 18)

**Pseudocode**:

mathematica

CopyEdit

`Start     Input age     If age >= 18 Then         Output "You are eligible to vote."     Else         Output "You are not eligible to vote."     End If End`

**Edge Cases to Consider**:

- Age = 18 (boundary condition)
    
- Negative age (optional validation)
    
- Decimal values (optional handling)
    

---

### 🎯 Key Takeaway

Pseudocode helps you:

- Think **logically**
    
- Focus on **problem-solving**, not syntax
    
- **Plan before coding**, reducing bugs and confusion
    

You’ll use this skill throughout your programming journey — especially in writing algorithms and designing logic-heavy solutions.
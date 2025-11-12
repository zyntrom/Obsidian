## 🧠 **Topic 1.8 – Disproof Techniques**

### **1️⃣ Valid Arguments**

|Concept|Explanation|
|---|---|
|**Definition**|An argument is **valid** if, whenever all its premises are true, the **conclusion must also be true**. Validity concerns logic, not real-world truth.|
|**Purpose**|Understanding validity helps identify flawed reasoning when attempting to **disprove** statements.|

**Example (Valid):**  
All even numbers are divisible by 2.  
8 is even.  
∴ 8 is divisible by 2. ✅

**Example (Invalid):**  
All programmers use Python.  
Alex uses Python.  
∴ Alex is a programmer. ❌ (Conclusion doesn’t necessarily follow.)

---

### **2️⃣ What Is Disproof?**

|Concept|Explanation|
|---|---|
|**Definition**|To **disprove** a statement means to **show it is not true in every case**.|
|**Goal**|Identify at least **one counterexample** or logical flaw that invalidates the claim.|
|**Relevance in CS**|Reveals logic or algorithmic flaws, aids debugging, and supports rigorous reasoning.|

**Key Idea:**  
✅ A single counterexample is enough to disprove a universal statement.

---

### **3️⃣ Techniques of Disproof**

|No.|Technique|Explanation|Example|
|---|---|---|---|
|**1**|**Counterexample**|Show one clear case where the statement fails.|“All birds can fly” → Ostrich disproves it.|
|**2**|**Logical Inconsistency**|Demonstrate that the statement contradicts itself or logic.|“I am inside and outside the room simultaneously.”|
|**3**|**Contradiction**|Assume the statement is true, derive an impossibility → therefore false.|To disprove “only finitely many primes,” assume it, derive contradiction.|
|**4**|**Reductio ad Absurdum**|Assume the claim and extend it to an absurd result.|“All cars are blue” → absurd generalization from one case.|
|**5**|**Inductive Counterexample**|Show a **pattern** of failures or repeated instances that contradict the claim.|“All apples are sweet” → find a sour apple.|
|**6**|**Empirical Observation**|Use experiment / data to contradict predictions.|“All metals expand when heated” → find one that contracts.|

---

### **4️⃣ Why Disproof Matters**

- Detects **faulty logic** early.
- Prevents **bugs** in algorithms and proofs.
- Encourages **critical thinking** in design and reasoning.
- Reinforces validity: knowing **why something fails** is as important as knowing why it works.

---

### **5️⃣ Steps to Disprove a Statement**

1. **Understand the Claim** → Identify its form (“for all x”, “there exists”, etc.).
2. **Check Logical Structure** → Are premises connected correctly?
3. **Search for a Counterexample** → One instance is sufficient to refute “for all”.
4. **Apply Logical Techniques** → Contradiction / Inconsistency / Observation.
5. **State Clearly** → Show the exact reason or instance that fails.

---

### **6️⃣ Summary Sheet**

|Concept|Key Points|
|---|---|
|**Valid Argument**|Premises → Conclusion (logically necessary).|
|**Disproof Goal**|Show statement not true in all cases.|
|**Main Methods**|Counterexample · Contradiction · Logical Inconsistency · Reductio ad Absurdum · Empirical Test|
|**Counterexample Rule**|One counterexample is enough to disprove “∀x P(x)”.|
|**Empirical Role**|Real-world testing of logical claims (e.g., experiments).|
|**Use in CS**|Debugging, verifying algorithms, checking logical soundness.|

---

### **7️⃣ Common Mistakes**

- Assuming that a **single example proving true** confirms a universal claim.
- Mixing **validity** (logic) with **truth** (real-world fact).
- Ignoring **premise-to-conclusion linkage**.
- Giving vague or incomplete counterexamples.

---

### **8️⃣ Quick Exam Pointers**

- Define **valid argument** clearly.
- Differentiate **proof** vs **disproof**.
- For each method, give **one concise example**.
- Remember: **1 counterexample = disproof**.
- **Contradiction** → Assume true → derive falsehood.
- **Reductio ad Absurdum** → Assume true → derive absurd result.

---

### **9️⃣ Practice Tasks**

1. Disprove: “All numbers are divisible by 2.”
2. Find a counterexample: “If n² is even, then n is even for all n.”
3. Identify the invalid reasoning:
    - “If A → B, and B is true, then A is true.”
4. Use empirical observation to challenge a scientific claim.

---

### **🔟 Revision Snapshot**

- **Validity = Logical connection**, not truth.
- **Disproof = Expose exception or contradiction.**
- **Techniques:**
    - Counterexample
    - Logical inconsistency
    - Contradiction
    - Reductio ad Absurdum
        
    - Inductive Counterexample
        
    - Empirical Observation
        
- **Goal:** Strengthen reasoning and debug logical errors.
## 🧠 Lesson 1.2: Logic — From Propositions to Predicates

---

### 🏁 Introduction

Have you ever wondered how Siri, Alexa, or Google seems to “understand” you?  
In reality, machines don’t understand like humans — they **follow strict logical rules** that decide what’s **true or false**.

> 💡 Logic = the foundation of decision-making in computers and AI.

Everything — from calculators to self-driving cars — relies on **logic** to process inputs and make consistent, rule-based decisions.

---

### ⚙️ What is Logic?

**Logic** is the **systematic process** of making decisions or drawing conclusions based on **true (T)** or **false (F)** statements.

It removes emotion and guesswork, replacing them with **structured reasoning** that both humans and machines can follow.

> Think of logic as the “grammar” of thinking — the rules that govern valid reasoning.

---

### 💡 Example: Smart Home Logic

**Scenario:** You want lights to turn ON only when:

1. It’s dark outside (P)
2. Someone is in the room (Q)

**Logical Expression:**

```
P ∧ Q → Light ON
```

|It is dark (P)|Someone in room (Q)|Light ON? (P ∧ Q → ON)|
|---|---|---|
|True|True|✅ Yes|
|True|False|❌ No|
|False|True|❌ No|
|False|False|❌ No|

> The system checks truth conditions, not emotions — just **pure logic**.

---

## 🧩 Propositional Logic

**Definition:**  
Propositional logic deals with **statements (propositions)** that are **true or false**, and combines them using logical connectives.

```embed
title: "An Introduction to Propositional Logic"
image: "https://i.ytimg.com/vi/5NGKbiA04Cw/maxresdefault.jpg"
description: "An introduction to propositions, truth tables, and logical equivalence, and logical operators — including negation, conjunction, disjunction, and implication..."
url: "https://youtu.be/5NGKbiA04Cw"
favicon: ""
aspectRatio: "56.25"
```

**Connectives:**

|Symbol|Meaning|Example|
|---|---|---|
|¬P|NOT P|“It is **not** raining.”|
|P ∧ Q|AND|“It is dark **and** cold.”|
|P ∨ Q|OR|“It is dark **or** cold.”|
|P → Q|IF...THEN|“If it rains, the ground gets wet.”|
|P ↔ Q|IF AND ONLY IF|“I pass the test **if and only if** I study.”|

---

### 🧮 Truth Table Example

```
P → Q
```

|P|Q|P → Q|
|---|---|---|
|T|T|T|
|T|F|F|
|F|T|T|
|F|F|T|

> In logic, **a false condition automatically makes the implication true** unless the first part (P) is true and the second (Q) is false.

---

## 🔍 Predicate Logic (First-Order Logic)

**Why Predicate Logic?**  
Propositional logic treats entire sentences as a single block.  
But what if we want to **analyze the parts inside** a statement?

```embed
title: "PREDICATE LOGIC and QUANTIFIER NEGATION - DISCRETE MATHEMATICS"
image: "https://i.ytimg.com/vi/gyoqX0W-NH4/maxresdefault.jpg"
description: "Today we wrap up our discussion of logic by introduction quantificational logic. This includes talking about existence and universality. We also discuss the ..."
url: "https://youtu.be/gyoqX0W-NH4"
favicon: ""
aspectRatio: "56.25"
```

Example:

> “All humans are mortal.”  
> In propositional logic → just `P`.  
> But predicate logic lets us say **who** is human and **what** property they have.

---

### ✳️ Predicate Logic Example

Let:

```
M(x): x is a man
Mortal(x): x is mortal
s: Socrates
```

**Statements:**

```bash
1. ∀x (M(x) → Mortal(x))   # All men are mortal
2. M(s)                    # Socrates is a man
∴ Mortal(s)                # Therefore, Socrates is mortal
```

> This allows reasoning about **objects and their properties**, not just whole statements.

---

### 🧠 Quantifiers in Predicate Logic

|Symbol|Name|Meaning|Example|
|---|---|---|---|
|∀|Universal Quantifier|“For all…”|∀x (Human(x) → Mortal(x))|
|∃|Existential Quantifier|“There exists…”|∃x (Prime(x) ∧ Even(x))|

> Quantifiers let us describe general or specific truths in logic and AI.

---

## 🧩 Rules of Inference

**Definition:**  
Rules of inference are logical steps that allow us to derive **new truths** from known premises — the “grammar” of reasoning.

![[Pasted image 20251112142025.png]]
---

### 📘 Common Rules of Inference

#### 1️⃣ Modus Ponens (Direct Reasoning)

```
If P → Q
P
∴ Q
```

Example:  
If it rains, the ground gets wet.  
It is raining.  
∴ The ground gets wet.

---

#### 2️⃣ Modus Tollens (Contrapositive Reasoning)

```
If P → Q
¬Q
∴ ¬P
```

Example:  
If power is out, lights won’t work.  
Lights are working.  
∴ Power is not out.

---

#### 3️⃣ Hypothetical Syllogism (Chain Reasoning)

```
If P → Q
If Q → R
∴ P → R
```

Example:  
If I study → I pass.  
If I pass → I graduate.  
∴ If I study → I graduate.

---

#### 4️⃣ Disjunctive Syllogism (Either-Or Elimination)

```
P ∨ Q
¬P
∴ Q
```

Example:  
Either I walk or take the bus.  
I’m not walking.  
∴ I’ll take the bus.

---

#### 5️⃣ Addition (Adding Options)

```
P
∴ P ∨ Q
```
Example:  
I completed my assignment.  
∴ I completed my assignment **or** watched TV.

---

#### 6️⃣ Simplification (Breaking Down Conjunctions)

```
P ∧ Q
∴ P
```

Example:  
I exercised and drank water.  
∴ I exercised.

---

#### 7️⃣ Conjunction (Combining Statements)

```
P
Q
∴ P ∧ Q
```

Example:  
I submitted the form.  
I emailed the teacher.  
∴ I submitted the form and emailed the teacher.

```embed
title: "Methods of Proof"
image: "https://i.ytimg.com/vi/qig_VH-YUJs/maxresdefault.jpg"
description: "Covers the different proof methods"
url: "https://youtu.be/qig_VH-YUJs"
favicon: ""
aspectRatio: "56.25"
```

---

## 🧩 Summary

|Concept|Description|
|---|---|
|**Logic**|The science of valid reasoning; foundation of computation and AI.|
|**Propositional Logic**|Deals with whole statements that are true/false.|
|**Connectives**|AND (∧), OR (∨), NOT (¬), IF…THEN (→), IFF (↔).|
|**Truth Tables**|Evaluate all combinations of truth values.|
|**Predicate Logic**|Extends propositional logic with variables, predicates, and quantifiers (∀, ∃).|
|**Rules of Inference**|Formal rules for valid reasoning (e.g., Modus Ponens, Modus Tollens).|

---

## 🎯 Real-World Applications

|Domain|Use of Logic|
|---|---|
|**AI & Machine Learning**|Decision-making and reasoning systems|
|**Databases**|Query formulation using predicates|
|**Programming**|Conditional statements and algorithm control|
|**Automation**|Smart systems and rule-based triggers|
|**Digital Circuits**|Logical gates (AND, OR, NOT) based on propositional logic|

---

## 🧩 Activity: Logic in Action

Explore how logic appears in real-world technologies like:

- Smart homes (conditional triggers)
- AI chatbots (predicate reasoning)
- Search engines (query logic)
- Software testing (assertions and inferences)

---

## 🧠 Bonus Resources

- [Introduction to Logic – Coursera](https://www.coursera.org)
- [Propositional Logic – GeeksforGeeks](https://www.geeksforgeeks.org)
- [Predicate Logic – GeeksforGeeks](https://www.geeksforgeeks.org)
- [Difference between Propositions & Predicates – Tutorialspoint](https://www.tutorialspoint.com)
- [Brilliant.org – Propositional Logic](https://brilliant.org)

![[Pasted image 20251112142343.png]]
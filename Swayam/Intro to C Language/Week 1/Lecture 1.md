# **Introductory Programming in C – Lecture 1 Notes**

### 🧑‍🏫 Course Overview & Introduction to Problem Solving with Algorithms

---

## 🎯 Course Objectives

- Learn how to **write basic and medium-sized programs** in the **C programming language**.
- Understand how to **solve problems using a computer**.
- Gain a skill that is increasingly considered **as fundamental as mathematics**.
- No prior programming experience assumed – **starts from scratch**.

---

## 💡 Why Learn Programming?

- **Enhances any skill set** – useful across disciplines:
    - Engineering
    - Sciences
    - Arts
- **Programming = Problem Solving**
- Programming skills open up pathways in:
    - Software development
    - Data science
    - System automation
    - Research computation

---

## ⚙️ Programming Process – 3 Key Steps

### 1. **Problem Definition**

- Often, real-world problems are **vague** or **imprecise**.
- First step: make the problem **precise** and **well-defined**.
- **In this course:** You are given **well-defined problems**, so this step is assumed already done.

---

### 2. **Developing a Logical Solution**

- A **logical solution** is a **finite set of steps**.
- These steps are known as an **algorithm**.
    
#### 🔑 Definition: Algorithm

> A finite, step-by-step procedure to solve a problem.

#### 📌 Key Features:

- Clear sequence of operations.
- Can involve:
    - Conditionals (if...then...else)
    - Loops (repeat until...)

#### 🔁 Algorithm Visualization:

- Often represented using **flowcharts**, especially useful for beginners.

---

### 3. **Implementation**

- The algorithm is then **translated into a programming language** (in this course, **C**).
- This produces a **working program**.

---

## 🧠 Familiar Examples of Algorithms

### 🍲 Cooking Recipe = Informal Algorithm

- Recipes have:
    - A list of **ingredients**
    - A series of **instructions** (steps)
- Not always fully precise, e.g.:
    - "Heat oil" assumes prior knowledge.
    - "Scoop size = your fist" is vague.

✅ Programming algorithms must be **precise** and **unambiguous**.

---

### 🪑 DIY Furniture Kit

- Comes with **step-by-step assembly instructions**.
- Easy for beginners to follow → just like algorithms in programming.

---

## 🧭 Flowcharts: Visual Representation of Algorithms

### 📐 Common Symbols:

|Symbol|Shape|Purpose|
|---|---|---|
|Start / End|Oval/Circle|Begin or terminate the flowchart|
|Input / Output|Parallelogram|Accept input or display output|
|Process|Rectangle|Operation or computation step|
|Decision|Diamond|Conditional test (yes/no, true/false)|

---

### 🧮 Example 1: Sum of First N Numbers

#### Problem: Compute the sum of integers from 1 to N.

#### Steps:

1. Input N
2. If N < 1 → nothing to do
3. Initialize sum = 0 and counter i = 1
4. Loop:
    - Add i to sum
    - Increment i
    - If i ≤ N, repeat
5. Output the final sum
6. End

#### 🔁 Algorithm Pattern:

```
Start 
Input N 
If N < 1 → End 
sum ← 0 
i ← 1 
While i ≤ N:     
	sum ← sum + i     
	i ← i + 1 
Output sum 
End
```

---

### 🧮 Example 2: Factorial of N (N!)

#### Problem: Compute N! = 1 × 2 × 3 × ... × N

#### Similar to sum algorithm, but:

- Initialize `product = 1`
- Instead of `sum += i`, do `product *= i`

#### Flowchart and algorithm structure is nearly identical.

---

## 🧾 Summary of Key Concepts

|Concept|Description|
|---|---|
|**Programming**|Writing a sequence of instructions to solve problems|
|**Algorithm**|Finite, logical step-by-step procedure|
|**Flowchart**|Graphical representation of an algorithm|
|**Implementation**|Writing code (in C) based on algorithm|
|**Real-world analogy**|Recipes, DIY kits = informal algorithms|

---

## ✅ Key Takeaways

- This course builds **step-by-step** from no prior experience.
- **Problem-solving using algorithms** is the core of programming.
- **C programming** is just a tool to express the logic clearly and efficiently.
- **Clarity and precision** are crucial in both algorithms and code.
- Beginners should **practice using flowcharts** for better understanding.
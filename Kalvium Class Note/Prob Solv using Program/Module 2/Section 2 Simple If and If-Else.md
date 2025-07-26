# **🧠 Control Structures: Simple If, If-Else & Ternary Operator**

---

## **1. 🌟 What Are Control Structures?**

Control structures help a program make **decisions** and **control the flow** of execution based on conditions.

Real-life analogy:  
👉 “If I roll a 6, I get a bonus turn.”  
Programming analogy:  
👉 “If the score is above 80, print 'You passed!'”

---

## **2. ✅ Simple If Statement**

### **Syntax (Python):**

```python
score = 85  
if score >= 80:  
  print("You passed!")
```

### **Explanation:**

- Checks **one condition**.
- If it's **true**, executes the block inside `if`.
- If **false**, it does **nothing**.

---

## **3. 🔀 If-Else Statement**

### **Syntax (Python):**

```python
weather = "rainy"  
if weather == "sunny":  
  print("Go for a walk")  
else:  
  print("Stay inside")
```

### **Explanation:**

- Provides **two options**.
- If condition is true → executes `if` block.
- If condition is false → executes `else` block.

### **Key Points:**

- Only **one** of the blocks runs.
- Always results in **some** action.

---

## **4. ⚡ Ternary Operator (Short If-Else)**

### **Syntax (Python):**

```python
score = 72  
result = "You passed!" if score >= 80 else "You failed."  
print(result)
```

### **Syntax (C++):**

```c++
int score = 72;  
string result = (score >= 80) ? "You passed!" : "You failed.";  
cout << result;
```

### **Explanation:**

- One-line shortcut for if-else.
- Format:  
      **condition ? true_output : false_output**
- Used mainly for **simple assignments or print operations**.

---

## **5. 🎯 Problem Example**

**Problem:** Build a grading system using the ternary operator.
### **Logic:**

- If score ≥ 80 → print "You passed!"
- Else → print "You failed."

**Result with score = 72:** You failed.

---

## **6. 🧪 Summary Table**

|Structure|Condition True|Condition False|
|---|---|---|
|`if`|Executes block|Does nothing|
|`if-else`|Executes `if` block|Executes `else` block|
|`ternary`|Executes `true` part|Executes `false` part|

---

## **7. 🧠 Real-Life Application**

- **Voting App**: If age ≥ 18 → allow vote.
- **Shopping App**: If cart value ≥ 500 → apply discount.
- **Game**: If health = 0 → game over.
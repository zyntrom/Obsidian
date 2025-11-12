## 📘 Lesson Summary: Introduction to Control Structures

**Module:** Control Structures  
**Topic Type:** Core Programming Logic

---

### 🧠 What Are Control Structures?

Control structures are the _decision-making_, _repetition-handling_, and _flow-guiding_ tools of any program.

Without them, your code would just run line-by-line — no decisions, no loops, no interactivity.

---

### 🛠️ Types of Control Structures

|Type|Purpose|Example Use Case|
|---|---|---|
|**Sequential**|Execute step-by-step instructions|Reading user input, then printing result|
|**Selection**|Make decisions using conditions|Choose clothing based on the weather|
|**Iteration**|Repeat tasks while condition holds true|Print numbers 1 to 10|

---

### 🔹 1. Sequential Control Structure

**Straightforward flow**, executed one line after another.

#### ✅ Example (Python):

```python
print("Open the fridge") 
print("Take out the milk") 
print("Pour into glass")
```

#### ✅ Example (cpp):

```cpp
cout << "Open the fridge" << endl; cout << "Take out the milk" << endl; cout << "Pour into glass" << endl;
```

🧾 _Think of it as reading a recipe line-by-line with no skips or repeats._

---

### 🔸 2. Selection (Conditional) Control Structure

Makes decisions using conditions like:

- `if`
- `else if`
- `else`
- `switch` (in C/cpp)

#### ✅ Python:

```python
number = 5 
if number > 0:     
	print("Positive") 
else:     
	print("Zero or Negative")
```

#### ✅ cpp:

```cpp
int number = 0; 
if (number == 0)     
	cout << "Zero"; 
else     
	cout << "Not zero";
```

🧾 _It’s like choosing between clothes based on the weather: “If it’s cold → wear jacket.”_

---

### 🔁 3. Iteration (Looping) Control Structure

Repeats a block of code until a condition is no longer true.

#### ✅ Python `for` loop:

```python
for i in range(5):
	print(i)
```

#### ✅ cpp `for` loop:

```cpp
for (int i = 0; i < 5; i++) {     
cout << i << endl; 
}
```

#### ✅ cpp `do-while` loop (runs at least once):

```cpp
int count = 0; do {     
cout << count << endl;     
count++; }while (count < 5);
```

🧾 _Think: brushing teeth daily – it repeats every day, conditionally._

---

### 🔍 Quick Comparison Table

|Feature|Sequential|Selection|Iteration|
|---|---|---|---|
|**Control Flow**|Line-by-line|Based on condition|Based on repeat condition|
|**Keywords**|None|`if`, `else`, `switch`|`for`, `while`, `do-while`|
|**Real-life Analogy**|Recipe steps|Choose clothes|Brush teeth daily|

---

### ✅ Best Practices with Control Structures

- **Use Clear Variable Names:** e.g. `temperature` > `x`
- **Keep Logic Simple:** Avoid too many nested `if` or loops
- **Comment When Needed:** Explain why a condition matters
- **Pick the Right Structure:** `for` for fixed loops, `while` for unknown counts

---

### 🔗 Bonus Resources:

- Control Structures | Educba
- [Control structures in computer programming | Britannica](https://www.britannica.com/topic/control-structure)

---

### 🚀 Final Words

Control structures are what make your code _think_. They give your program the ability to:

- Decide
- Repeat
- React
- Adapt

You’ve now learned the **three fundamental ways** all programs control behavior. Mastering these will unlock **real programming power** in your future projects.

---

Would you like to:

- ✅ Practice with **if-else**, `for` and `while`?
- 🧪 Get a **quiz** to reinforce this?
- 📚 Jump to the next topic: **Simple If and If-Else**?
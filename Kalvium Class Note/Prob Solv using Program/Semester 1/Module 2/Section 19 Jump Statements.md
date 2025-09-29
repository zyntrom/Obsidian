## 🚀 Jump Statements – SPE 2025

Jump statements allow us to **change the normal flow** of a program, helping us **exit loops early**, **skip iterations**, or **return** values from functions.

---

### 🔹 What are Jump Statements?

They are used to:

- Exit loops/functions early
- Skip certain iterations in loops
- Directly jump to a labeled statement (cpp only)

These include:

1. **break**
2. **continue**
3. **return**
4. **goto** (cpp only)

---

### 1️⃣ Break Statement

#### 🔧 Function:

Exits the loop **immediately**, skipping remaining iterations.

#### ✅ Use Case:

Stop processing once a condition is met.

#### Python Example:

```python
for i in range(1, 11):  
 if i == 5:  
  break  
 print(i, end=" ")  
```

```
Output: 1 2 3 4
```

#### cpp Example:

```cpp
for (int i = 1; i <= 10; i++) {  
 if (i == 5) break;  
 cout << i << " ";  
}  
```

```
Output: 1 2 3 4
```

---

### 2️⃣ Continue Statement

#### 🔧 Function:

Skips the current iteration, continues with the next.

#### ✅ Use Case:

Skip processing for some specific values.

#### Python Example:

```python
for i in range(1, 11):  
 if i % 2 == 0:  
  continue  
 print(i, end=" ")  
```

```
Output: 1 3 5 7 9
```

#### cpp Example:

```cpp
for (int i = 1; i <= 10; i++) {  
 if (i % 2 == 0) continue;  
	 cout << i << " ";  
}  
```

```
Output: 1 3 5 7 9
```

---

### 3️⃣ Return Statement

#### 🔧 Function:

Exits a function and optionally returns a value.

#### ✅ Use Case:

Used when a function finishes execution.

#### Python Example:

```python
def sum(a, b):  
	return a + b  
	print(sum(5, 3))  
```

**Output**: 8

#### cpp Example:

```cpp
int sum(int a, int b) {  
	return a + b;  
}  

int main() {  
	cout << sum(5, 3);  
	return 0;  
}
```

**Output**: 8

---

### 4️⃣ Goto Statement (Only in cpp)

#### 🔧 Function:

Jumps to a labeled line in the code.

#### ⚠️ Use Case:

Only if absolutely necessary — discouraged in modern code.

#### cpp Example:

```cpp
int num = 10;  
if (num == 10) 
goto label;  
cout << "Skipped this!";  
label:  
cout << "Jumped to label!";  
```
Output: Jumped to label!

#### ⚠️ Warning:

Avoid unless there's no cleaner alternative. Makes code hard to read and debug.

---

### ✅ Best Practices

- ✔ Use **`return`** to exit functions clearly.
- ✔ Use **`break`**/**`continue`** to write concise loops.
- ❌ Avoid **`goto`** when possible.

---

### 💡 Why Use Jump Statements?

- Make code **efficient** (skip or stop as needed).
- Improve **readability** (clear logic flow).
- Avoid **redundant processing**.
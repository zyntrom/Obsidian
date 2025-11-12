## 📘 While Loop – Notes (SPE 2025 | Control Structures)

### 🧠 What is a While Loop?

A **while loop** is used to **repeat a block of code as long as a condition is true**.

Use it when:

- You **don’t know in advance** how many times something should run.
- You want to **repeat something until** a condition changes.

---

### 🔁 Syntax

#### ✅ Python

```python
i = 1 
while i <= 5:     
	print(i)     
	i += 1
```

#### ✅ cpp

```cpp
int i = 1; 
while (i <= 5) {     
	cout << i << endl;     
	i++; 
}
```

---

### ⚠️ Avoid Infinite Loops

Always update a value inside the loop, or it may run **forever**!

```cpp
# Infinite loop example (❌) 
i = 1 
while i <= 5:     
	print(i) 
	# Fix it with: i += 1
```

---

### 💡 Real-World Analogy: Filling a Glass

Repeat adding water **until the glass is full**.

#### ✅ Python

```python
water = 0 
glass_capacity = 5 
while water < glass_capacity:     
	water += 1     
	print("Added water. Current level:", water) 
print("The glass is full!")
```

#### ✅ cpp

```cpp
int water = 0; 
int glassCapacity = 5; 
while (water < glassCapacity) {     
	water++;     
	cout << "Added water. Current level: " << water << endl; 
} 
cout << "The glass is full!" << endl;
```

---

### 🔄 Use Cases

- **Games** (e.g., keep guessing until correct)
- **Timers** (e.g., countdowns)
- **Sensor checks** (e.g., while temperature > limit)
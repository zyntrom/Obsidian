# 📘 Arrays – Notes

---

## 1. What is an Array?

- **Definition**: A **linear data structure** that stores multiple elements of the **same data type** in **contiguous memory** locations.
- **Analogy**: Like train compartments or lockers, each holding one item, arranged in sequence.
- **Key Property**: Each element has a unique **index (position)**.

---

## 2. Memory Representation of Arrays

- Elements stored in **contiguous memory locations**.
- Position of element = `Base Address + (Index × Size of Data Type)`.
- Example: If int = 4 bytes, first element at `1000`, then →
    - 2nd at `1004`, 3rd at `1008`, etc.

![[Pasted image 20250824223713.png]]

---

## 3. Indexing in Arrays

- Arrays are usually **zero-indexed**.
- First element → index `0`.
- Example: `scores[0]` = first element, `scores[2]` = third element.
- Analogy: Books on a shelf → third book = position 2.

```embed
title: "Arrays Explained Visually"
image: "https://i.ytimg.com/vi/2o8jmdz1TiY/maxresdefault.jpg"
description: "In this video, I've explained the concept of arrays in just 10 minutes using animations and pseudocode. We cover initialization, access, modification, insert..."
url: "https://youtu.be/2o8jmdz1TiY"
favicon: ""
aspectRatio: "56.25"
```

---

## 4. Basic Operations on Arrays

### (a) Initialization

**Python**

```python
numbers = [10, 20, 30, 40, 50]   # With values 
numbers = []                     # Empty list
```

**C++**

```c++
int numbers[] = {10, 20, 30, 40, 50}; 
int empty_array[5];   // Uninitialized, fixed size
```
---

### (b) Insertion

**Python**

```python
numbers = [0] * 5 
numbers[0] = 10 
numbers[3] = 40
```

**C++**

```c++
int numbers[5]; 
numbers[0] = 10; 
numbers[3] = 40;
```

✅ Index range = `0 → size-1`

---

### (c) Retrieval

**Python**

```python
numbers = [10, 20, 30, 40, 50] 
first = numbers[0] 
fourth = numbers[3]
```
**C++**

```c++
int numbers[] = {10, 20, 30, 40, 50}; 
int first = numbers[0]; 
int fourth = numbers[3];
```

---

### (d) Traversal (Loops)

**Python**

```python
numbers = [10, 20, 30, 40, 50] 
for i in range(5):     
	print(numbers[i])
```

**C++**

```c++
int numbers[] = {10, 20, 30, 40, 50}; 
for (int i = 0; i < 5; i++) {     
	cout << numbers[i] << endl; 
}
```

---

## 5. Types of Arrays

### (a) Based on Size

- **Fixed Size Arrays**
    - Size declared at start, **cannot change**.
    - Risk: memory wastage or shortage.
- **Dynamic Size Arrays**
    - Can grow/shrink at runtime.
    - Examples: Python `list`, C++ `vector`, Java `ArrayList`.

![[Pasted image 20250824223745.png]]

---

### (b) Based on Dimensions

- **1D Array**: Single line of elements (e.g., marks of students).
![[Pasted image 20250824223800.png]]
- **2D Array**: Rows & columns like a table (e.g., student marks in subjects). 
![[Pasted image 20250824223811.png]]
- **Multi-Dimensional Array**: Higher-level (3D, etc.) → cube-like structure (e.g., Rubik’s cube, 3D modeling).

---

## 6. Practice Problems

### (a) Warm-up

- Create array of first 5 natural numbers.
- Print 2nd number.

### (b) City Printer Program

- Create array of 5 cities.
- Use loop to print each city on a new line.

---

## 7. Summary

- Arrays = **store multiple values of same type in order**.
- Operations: **Create, Insert, Retrieve, Traverse**.
- Types: **Fixed vs Dynamic**, **1D vs 2D vs Multi-Dimensional**.
- Useful for structured, efficient storage in **programming & problem-solving**.
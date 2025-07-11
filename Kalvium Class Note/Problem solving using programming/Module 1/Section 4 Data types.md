## 🧠 Problem Solving Using Programming — Lesson 4 Notes

**Lesson Title:** _Data Types_  
**Module:** Getting Started with Problem Solving

---

### 📦 What Are Data Types?

- **Definition**: Data types tell the **compiler/interpreter** what kind of data is being stored and how to handle it.
- **Real-Life Analogy**: Like labeled jars in your kitchen — you don’t want to mistake salt for sugar!
- **Purpose**: Helps the computer understand the **type, size, and operations** allowed on a piece of data.

---

## 🧩 Common Data Types in Programming

---

### 🧱 1. Primitive Data Types

These are the **most basic, built-in** data types. They hold **single values** and form the foundation of programming.

|Type|Description|Examples|
|---|---|---|
|**int**|Whole numbers (no decimal)|`1`, `-100`, `50`|
|**float**|Decimal numbers (need precision)|`3.14`, `-0.5`, `99.99`|
|**char**|A single character or symbol|`'A'`, `'z'`, `'?'`|
|**bool**|True or False values (logical decisions)|`True`, `False`|

🧪 **Python Note**: No separate `char` type — use single-character strings  
🧪 **C++ Note**: You must declare the type (static typing)

#### 🚨 Type Error Example:

`result = 5 + "five"  # ❌ Error: Can't add integer and string`

---

### ✨ Data Type Modifiers (Mainly C++)

Modifiers **extend or limit** primitive types.

|Modifier|Description|Range (32-bit)|
|---|---|---|
|`unsigned int`|Only positive integers|`0` to `4,294,967,295`|
|`short int`|Small integers (2 bytes)|`-32,768` to `32,767`|
|`unsigned short int`|Small positive values|`0` to `65,535`|
|`long int`|Large numbers (8 bytes)|`±2,147,483,647`|
|`long long int`|Very large numbers (64-bit)|`±9 quintillion` range|

---

### 🧰 2. Composite Data Types

These are **collections** of primitive types bundled together.

|Type|Description|Examples|
|---|---|---|
|**Array**|Fixed-size collection of same-type elements|`int marks[4] = {85, 90, 78, 92};`|
|**List**|Resizable collection (Python: mixed types)|`shopping_list = ["milk", "bread"]`|
|**Tuple**|Immutable ordered collection|`student = ("Maya", 18, True)`|
|**Object**|Instance of class (encapsulates data + methods)|See below|

#### 📌 Python Object Example:

`class Student:     def __init__(self, name, grade):         self.name = name         self.grade = grade     def attend_class(self):         print(f"{self.name} is attending class.")`

#### 📌 C++ Object Example:

`class Student { public:     string name;     int grade;     void attendClass() {         cout << name << " is attending class." << endl;     } };`

---

### 🛠️ 3. User-Defined Data Types

When built-in types are not enough, you can create your **own custom types** using:

|Type|Purpose|
|---|---|
|**struct**|Groups variables of different types (C++)|
|**class**|Combines data and methods (OOP foundation)|
|**enum**|Set of named constant values (for choices/states)|

🧠 **Real-World Example**: Instead of separate variables for a player's name, health, and status — use a `Player` class or `struct`.

---

### 🧮 Data Type Sizes (Memory & Range)

|Data Type|Size|Range/Notes|
|---|---|---|
|`char`|1 byte|`0–255` (ASCII), `0–65,535` (Unicode)|
|`int`|4 bytes|`-2,147,483,648` to `2,147,483,647`|
|`unsigned int`|4 bytes|`0` to `4,294,967,295`|
|`short`|2 bytes|`-32,768` to `32,767`|
|`long`|8 bytes|Very large whole numbers|
|`float`|4 bytes|`±3.4e−38` to `±3.4e+38`|
|`double`|8 bytes|`±1.7e−308` to `±1.7e+308`|
|`boolean` / `bool`|1 byte|`true` or `false`|

---

### 💡 Why Does Size & Range Matter?

- **Memory Optimization**: Pick the smallest suitable type.
- **Performance**: Smaller types = faster execution.
- **Accuracy**: `float` vs `double` for precision needs.
- **Safety**: Prevent overflow/underflow using appropriate types (e.g., unsigned for non-negative values).

---

### 🎉 Summary

|Data Type Category|Examples|Used For|
|---|---|---|
|**Primitive**|`int`, `float`, `char`, `bool`|Simple, single-value storage|
|**Composite**|`list`, `array`, `object`, `tuple`|Grouping related data values|
|**User-Defined**|`struct`, `class`, `enum`|Custom structures for real-world modeling|
|**Modifiers (C++)**|`unsigned`, `short`, `long`, etc.|Fine-tuning memory usage and value range|

---
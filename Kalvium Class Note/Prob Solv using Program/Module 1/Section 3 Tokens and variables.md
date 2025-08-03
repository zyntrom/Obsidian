## 💻 Problem Solving Using Programming — Lesson 3 Notes

**Lesson Title:** _Tokens and Variables_  
**Module:** Getting Started with Problem Solving

---

### 🧩 What are Tokens?

**Tokens** are the **smallest meaningful components** of a programming language. During compilation or interpretation, code is broken into tokens through **lexical analysis**.

📌 **Think of tokens like grammar elements** in English — each one (noun, verb, etc.) adds meaning to a sentence. Similarly, tokens help computers make sense of code.

---

### 🧷 Types of Tokens

| Token Type                | Description                                                          |
| ------------------------- | -------------------------------------------------------------------- |
| **Keywords**              | Predefined reserved words used to define program structure and logic |
| **Identifiers**           | Names created by programmers (variables, functions, classes, etc.)   |
| **Literals**              | Fixed values used directly in the code (e.g., `5`, `"Hello"` )       |
| **Operators**             | Symbols that perform actions on data (e.g., +, -, == )               |
| **Delimiters**            | Characters that organize code (e.g., `()`, `{}`, `;`, `:`)           |
| **Comments & Whitespace** | Help explain and format code; ignored by the compiler                |

---

### 🔑 Keywords

**Keywords** are **reserved words** with **special meaning** in programming languages.  
You **cannot** use them as identifiers.

#### 📌 Python Keywords (some examples):

```
if, else, while, def, class, import, return, in, try, except, True, False, None
```

#### 📌 C++ Keywords (some examples):

```
int, float, char, if, else, switch, for, while, return, class, public, private, try, catch
```

---

### 🏷️ Identifiers

**Identifiers** are **user-defined names** for variables, functions, classes, etc.

#### ✅ Rules:

- Start with a **letter or underscore (_)**
- Can contain **letters, digits, underscores**
- **Cannot** start with a digit
- **Case-sensitive** in both Python and C++

#### 🐍 Python Naming Convention:

- **snake_case** is preferred  
    Example: `total_marks`, `student_name`

#### 💻 C++ Naming Convention:

- No enforced rule; commonly uses **camelCase** or **snake_case**  
    Example: `totalMarks`, `student_name`

---

### 🔢 Literals

**Literals** are **fixed, constant values** directly used in code.  
They don’t have names.

#### Examples:

- **Integer**: `100`, `0`, `-5`
- **Float**: `3.14`, `-0.01`
- **String**: `"Hello"`, `'World'`
- **Boolean**: `True`, `False`

---

### ➕ Operators

**Operators** perform **actions** on values (called operands).

#### Types:

- **Arithmetic**: `+`, `-`, `*`, `/`, `%`
- **Comparison**: `==`, `!=`, `>`, `<`, `>=`, `<=`
- **Assignment**: `=`, `+=`, `-=`, `*=`, etc.
- **Logical**: `and`, `or`, `not` (Python); `&&`, `||`, `!` (C++)

---

### 🔣 Delimiters

**Delimiters** organize code and define structure.

#### Common Delimiters in Python & C++:

|Delimiter|Purpose|Example|
|---|---|---|
|`()`|Grouping / Function call|`print("Hello")`|
|`[]`|List/Array indexing|`arr[0]`|
|`{}`|Block in C++|`int main() { ... }`|
|`:`|Code block start in Python|`if a > b:`|
|`,`|Separate arguments or items|`func(a, b, c)`|
|`;`|End statement in C++|`int x = 5;`|
|`.`|Access methods/attributes|`math.sqrt(16)` or `object.var`|

---

### 📝 Whitespace & Comments

|Feature|Python|C++|
|---|---|---|
|**Whitespace**|Used for indentation (significant)|Used to separate code (not significant)|
|**Single-line comment**|`# comment`|`// comment`|
|**Multi-line comment**|`'''comment'''` or `"""`|`/* comment */`|

---

### 🧪 Examples of Token Breakdown

#### 📌 Python:

python

CopyEdit

`variable = 5 + 3 print("Result: ", variable)`

**Tokens**:

- `variable` → Identifier
- `=` → Assignment Operator
- `5`, `3` → Literals
- `+` → Arithmetic Operator
- `print` → Built-in function (identifier)
- `(`, `)`, `","` → Delimiters

---

#### 📌 C++:

`int result = 5 + 3; std::cout << "Result: " << result << std::endl;`

**Tokens**:

- `int` → Keyword
- `result` → Identifier
- `=` → Operator
- `5`, `3` → Literals
- `+` → Operator
- `;` → Delimiter
- `std::cout` → Namespace-qualified identifier
- `"Result: "` → String literal
- `<<` → Output operator
- `endl` → Identifier (manipulator)
- `::` → Scope resolution operator

---

### 📦 Variables

A **variable** is a **named container** that stores data.  
It consists of:

- **Name** (identifier)
- **Type** (what kind of data)
- **Value** (actual data)

---

#### 🐍 Variables in Python

- **Dynamically typed** — no need to declare type
- Type inferred from assigned value

```python
age = 25          # int 
name = "ZynTrom"  # str 
pi = 3.14         # float
```

---

#### 💻 Variables in C++

- **Statically typed** — type must be declared
- Strict rules help avoid bugs

```c++
int age = 25; 
float pi = 3.14; 
char grade = 'A';
#include <iostream> 
using namespace std;  
int main() {     
	char name[] = "Kalvium";     
	int age = 1;     
	cout << name << endl;     
	cout << age;     
	return 0; 
}
```

📤 **Output:**

`Kalvium 1`

---

### ✍️ Group Exercise: Token Hunt & Variable Challenge

#### 1️⃣ **Token Hunt**

Write a simple code snippet using a variety of tokens.

Example:

```python
if score >= 50:     
print("Pass") else:     
print("Fail")
```

Then label the tokens:

- `if` = keyword
- `score` = identifier
- `>=` = operator
- `:` = delimiter
- `"Pass"` = literal

---

#### 2️⃣ **Variable Challenge**

✅ Valid variable names:

- `total_marks`
- `user_age`
- `temperature_celsius`

❌ Invalid/confusing names:

- `1stValue` (starts with digit)
- `my-variable` (invalid `-`)
- `class` (reserved keyword)

Then pass the paper around, review others’ answers, and give feedback.

---

### 🎯 Key Takeaway

Understanding **tokens** and **variables** gives you the foundation to:

- **Write clear, structured code**
- **Avoid common syntax errors**
- **Build logic that computers understand**
## 🧠 Lesson Notes: Type Casting and Modifiers

**Course:** Problem Solving Using Programming  
**Module:** Getting Started with Problem Solving  
**Lesson:** Type Casting and Modifiers  

---

### 🔄 What is Type Casting?

Type casting is **changing one data type into another**, like pouring juice into a different glass 🍹.

### 📌 Types of Type Casting

|Type|Description|Example|
|---|---|---|
|**Implicit**|Auto-conversion by compiler when safe|`int + float → float`|
|**Explicit**|Manual conversion by programmer|`float → int` (decimal part lost)|

---

### ✅ Python Examples

```python
#Implicit 
a = 10 b = 3.5 c = a + b    # int + float = float 
print(c)     # 13.5  
#Explicit 
x = 10.7 y = int(x) 
print(y)     # 10  
#String to int 
s = "123" 
num = int(s) 
print(num + 10)  # 133
```

---

### ✅ cpp Examples

```cpp
#include <iostream> 
#include <string> 
using namespace std;  
int main() {     
	// Implicit     
	int a = 5;     
	float b = 2.5;     
	float c = a + b;     
	cout << c << endl;  // 7.5      
	// Explicit     
	float x = 8.9;     
	int y = (int)x;     
	cout << y << endl;  // 8      
	// String to int     
	string s = "123";     
	int num = stoi(s);     
	cout << num + 10 << endl;  // 133 
}``
```

---

### 🏷️ What Are Modifiers? (cpp Only)

Modifiers are **keywords** that **change the size, range, or sign** of a data type — like adding a label on a glass: “Only positive!” or “Extra large!”

#### 🧾 Common cpp Modifiers:

|Modifier|Purpose|Range (32-bit system)|
|---|---|---|
|`signed int`|Default: allows negatives|−2,147,483,648 to 2,147,483,647|
|`unsigned int`|Only positives|0 to 4,294,967,295|
|`short int`|Smaller memory|−32,768 to 32,767|
|`unsigned short int`|Small positives only|0 to 65,535|
|`long int`|Bigger size|Similar to `int` on 32-bit|
|`unsigned long int`|Larger range for positives|0 to 4,294,967,295|
|`long long int`|Even larger|Very large negative to positive range|
|`unsigned long long`|Huge positive values only|0 to 18,446,744,073,709,551,615|

---

### 🍹 Fun Analogy: Juice Bar Edition

|Analogy Item|Programming Concept|
|---|---|
|🥤 `int`|Medium glass (whole numbers)|
|🧃 `float`|Measuring cup (decimals)|
|🍼 `double`|Tall jug (high-precision decimals)|
|🔄 Type Cast|Pouring between glasses|
|✏️ Modifier|Label (e.g. “only positive”)|

---

### ✨ Summary

| Concept       | Python          | cpp                                 |
| ------------- | --------------- | ----------------------------------- |
| Implicit Cast | Yes             | Yes                                 |
| Explicit Cast | `int(x)`        | `(int)x`                            |
| Modifiers     | ❌ Not Available | ✅ `unsigned`, `short`, `long`, etc. |
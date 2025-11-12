## 🧠 Problem

**Goal**: From a given lowercase input string, print **all the vowels** in the order they appear.

**Input**: A lowercase string (e.g., `kalvium`)  
**Output**: Vowels from the string (e.g., `aiu`)

---

## 🧮 Logic & Approach

- Vowels in lowercase: `a`, `e`, `i`, `o`, `u`
- Loop through each character in the string:
    - If it's a vowel, print it

---

## 🐍 Python Program

```python
s = input()  # Input string 
for ch in s:     
	if ch in 'aeiou':         
		print(ch, end="")
```

### 🔍 Explanation

- `for ch in s` → loops through each character
- `if ch in 'aeiou'` → checks if it’s a vowel
- `end=""` → prints without newline/space

---

## 💻 cpp Program

```cpp
#include <iostream> 
using namespace std;  
int main() {     
	string s;     
	cin >> s;  // Input string      
	for (int i = 0; i < s.length(); i++) {         
		char ch = s[i];         
		if (ch == 'a' || ch == 'e' || ch == 'i' || ch == 'o' || ch == 'u') {             
			cout << ch;         
			}     
		}     
	return 0; 
}
```

### 🔍 Explanation

- `s[i]` → accesses each character
- Check if character matches any vowel

---

## ✅ Sample Input & Output

**Input**

```
kalvium
```

**Output**

```
aiu
```

---
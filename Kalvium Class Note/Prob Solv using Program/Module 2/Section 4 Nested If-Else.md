# 🧠 Nested If-Else (SPE 2025 – Control Structures)

---

## 🗣️ Real-Life Analogy

Nested if-else is used when **one decision depends on another**.

**Example: Going for a walk**

- First check: Is it raining?
    - If yes → Do I have an umbrella?
        - If yes → Go for a walk
        - Else → Stay in
    - If no → Go for a walk

---

## 💡 Why Nested If-Else?

You use **nested logic** when:

- You want to perform a second check **only** if the first one is satisfied.
- Avoids unnecessary checks and ensures a logical flow.

---

## 🎬 Movie Example

### Python Version

```python
has_ticket = True 
age = 12  
if has_ticket:     
	if age >= 13:         
		print("You can watch the movie.")     
	else:         
		print("You are too young to watch the movie.") 
else:     
	print("You need a ticket to enter.")
```

### C++ Version

```c++
bool has_ticket = true; 
int age = 12;  
	if (has_ticket) {     
		if (age >= 13) {         
			cout << "You can watch the movie.";     } else {         cout << "You are too young to watch the movie.";     } } else {     cout << "You need a ticket to enter."; }
```

### ✅ Step-by-Step Logic:

1. **Check `has_ticket`**:
    
    - If `False`: print "You need a ticket."
        
    - If `True`: check age
        
2. **Check `age >= 13`**:
    
    - If `True`: print "You can watch the movie."
        
    - Else: print "You are too young."
        

---

## 🔍 Value Comparison Example

### Python

python

CopyEdit

`x = 10 y = 10  if x >= y:     if x == y:         print("Both are equal.")     else:         print("x is greater.") else:     print("y is greater.")`

### C++

cpp

CopyEdit

`int x = 10, y = 10;  if (x >= y) {     if (x == y) {         cout << "Both are equal.";     } else {         cout << "x is greater.";     } } else {     cout << "y is greater."; }`

### 🧠 Step-by-Step:

1. Outer check: `x >= y`
    
    - If `False`: y is greater
        
    - If `True`: check `x == y`
        
        - If `True`: both are equal
            
        - Else: x is greater
            

---

## ✍️ How to Write Nested If-Else

- Start with a primary `if`
    
- Inside that block, write another `if-else`
    
- You can nest as deep as needed (usually keep it to 1-2 levels)
    

### Example (Compare Two Numbers)

#### Python

python

CopyEdit

`a = 15 b = 25  if a == b:     print("Both numbers are equal.") else:     if a > b:         print("a is greater.")     else:         print("b is greater.")`

#### C++

cpp

CopyEdit

`int a = 15, b = 25;  if (a == b) {     cout << "Both numbers are equal."; } else {     if (a > b) {         cout << "a is greater.";     } else {         cout << "b is greater.";     } }`

---

## 🔁 Visualizing the Logic

Nested if-else works like a **decision tree**:

- One branch opens another
    
- Each condition unlocks the next layer
    
- Ensures **layered thinking** like:
    
    - "If it's Saturday"
        
        - "And if mom said yes"
            
            - "And if Wi-Fi is working"
                
                - "Then play Fortnite 🎮"
                    

---

## 📘 Summary

|**Concept**|**Explanation**|
|---|---|
|Nested If-Else|One `if` or `else` block **inside** another|
|Decision Dependency|Inner condition runs **only if** outer one does|
|Real-World Use|Logical flows like tickets + age or ID + entry|
|Python Style|Uses **indentation** for nesting|
|C++ Style|Uses **braces `{}`** for nesting|
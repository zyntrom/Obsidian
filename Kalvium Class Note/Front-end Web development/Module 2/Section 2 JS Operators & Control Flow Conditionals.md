## 📘 **Quick Revision Notes – JS Operators & Conditionals**

### 🎯 Learning Objectives:

- Understand JavaScript **operators** and how to use them
- Learn about **conditional statements** (`if`, `else`, `switch`)
- Use both to control how your program behaves

---

### 🔢 **JavaScript Operators**

#### 1. **Arithmetic Operators** — Used for math operations:


```js
+  // Addition 
-  // Subtraction 
*  // Multiplication 
/  // Division 
%  // Modulus (Remainder) 
** // Exponentiation
```

**Example:**

```js
let x = 10, 
y = 5; 
console.log(x + y); // 15
```

#### 2. **Assignment Operators** — Assign values with or without operations:

```js
=   // Assign 
+=  // Add & assign 
-=  // Subtract & assign 
*=  // Multiply & assign 
/=  // Divide & assign
```

**Example:**

```js
let x = 10; x += 5; // x = 15
```

#### 3. **Comparison Operators** — Compare values:

```js
==   // Equal (loose) 
===  // Equal (strict) !=   // Not equal (loose) !==  // Not equal (strict) >    // Greater than <    // Less than >=   // Greater than or equal <=   // Less than or equal
```

**Example:**

js

CopyEdit

`5 == "5"   // true 5 === "5"  // false`

#### 4. **Logical Operators** — Combine conditions:

js

CopyEdit

`&&  // AND ||  // OR !   // NOT`

**Example:**

js

CopyEdit

`true && false // false true || false // true !true         // false`

#### 5. **Other Operators**

js

CopyEdit

`? :         // Ternary: condition ? value_if_true : value_if_false typeof      // Returns the data type instanceof  // Checks if object is of a particular class`

---

### 🔁 **Conditional Statements**

Control the **flow of logic** in your code.

#### 1. **If Statement**

js

CopyEdit

`if (condition) {   // code runs if condition is true }`

#### 2. **If...else**

js

CopyEdit

`if (condition) {   // true block } else {   // false block }`

#### 3. **If...else if...else**

js

CopyEdit

`if (condition1) {   // block 1 } else if (condition2) {   // block 2 } else {   // default block }`

#### 4. **Switch Statement**

Best for multiple specific values.

js

CopyEdit

`switch (value) {   case "option1":     // do something     break;   case "option2":     // do something else     break;   default:     // default action }`

---

### 🧠 Summary

- **Operators** let JavaScript _calculate_, _assign_, _compare_, and _evaluate logic_.
    
- **Conditionals** guide the program to make decisions.
    
- Combine both to create **dynamic and interactive web experiences**.
    

---
## 🎯 Learning Objectives

By the end of this lesson, you should be able to:

- Use **pseudo-classes** to style elements based on **user interaction** or **position**
- Use **pseudo-elements** to style specific parts of an element or insert new content
- **Combine selectors** to apply complex styling rules

---

## 🟡 **Pseudo-Classes**

_Style elements based on their current **state**, **position**, or **user interaction**_

### 🔧 Syntax:

```css
selector:pseudo-class {   
	property: value; }
```

### 🔹 Common Pseudo-Classes:

|Pseudo-Class|Description|
|---|---|
|`:hover`|When mouse is over the element|
|`:active`|When element is being clicked|
|`:focus`|When element is focused (e.g., input box)|
|`:first-child`|First child of its parent|
|`:last-child`|Last child of its parent|
|`:nth-child(n)`|The nth child (odd/even/number)|

### 🧪 Example:

css

CopyEdit

```css
a:hover {   
	color: red; }  
input:focus {   
	background-color: lightyellow; }  
li:first-child {   
	font-weight: bold; }  
li:nth-child(odd) {   
	background-color: #f2f2f2; }
```

---

## 🟣 **Pseudo-Elements**

_Style **specific parts** of an element or insert **virtual content**_

### 🔧 Syntax:

```css
selector::pseudo-element {   
	property: value; }
```

### 🔹 Common Pseudo-Elements:

|Pseudo-Element|Description|
|---|---|
|`::first-line`|First line of a block of text|
|`::first-letter`|First letter of a block|
|`::before`|Insert content before the element|
|`::after`|Insert content after the element|
|`::placeholder`|Style placeholder text in inputs|
|`::selection`|Style text that the user selects|

### 🧪 Example:

```css
p::first-letter {   
	font-size: 2em;   
	color: #333; }  
input::placeholder {   
	color: gray;   
	font-style: italic; }  
.decorated::before {   
	content: "★ ";   
	color: gold; }  
.decorated::after {   
	content: " ★";   
	color: gold; }
```

---

## 🧩 **Combining Selectors**

Combine **pseudo-classes** and **pseudo-elements** for complex interactions.

### 🧪 Example:

```css
/* First paragraph's first letter turns red on hover */ 
p:first-child::first-letter:hover {   
	color: red; }  /* Show (end) after last list item on hover */ 
li:last-child:hover::after {   
	content: " (end)";   
	color: gray; }
```

---

## ✅ Summary

|Selector Type|Use Case|
|---|---|
|`:hover`, `:focus`|React to user interaction|
|`:first-child`|Target element position within parent|
|`::before`, `::after`|Insert content not in HTML|
|`::first-letter`, `::first-line`|Style parts of text|
|Combined Selectors|Apply rules based on **multiple conditions**|
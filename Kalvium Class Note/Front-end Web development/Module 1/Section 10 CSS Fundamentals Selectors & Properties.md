## 🧠 Learning Objectives

- Understand **CSS selectors** and their use
- Style elements using **tag, class, ID,** and **pseudo-class** selectors
- Build responsive, interactive designs with proper targeting

---

## 🎯 What are CSS Selectors?

**CSS selectors** are like _filters_ — they tell the browser **which HTML elements** should be styled.

Without them, all elements would look the same!

---

## 🔵 1. **Tag Name Selectors**

These apply styles to **all tags** of a specific type.

### 🧪 Example:

```html
<h1>Hello</h1> 
<p>This is a paragraph.</p>
```

```css
h1 {   
	color: blue; } 
p {   
	font-size: 16px; }
```


🔹 _All_ `<h1>` become blue  
🔹 _All_ `<p>` get 16px font

---

## 🟡 2. **Class Selectors (`.class`)**

Target **multiple** elements that share the same class.

### 🧪 Example:

```html
<p class="highlight">Important text</p> 
<div class="highlight">Special div</div>
```

```css
.highlight {   
	background-color: yellow;   
	padding: 10px; }
```

✅ Great for applying **common styles** to **many elements** regardless of tag type.

---

## 🔴 3. **ID Selectors (`#id`)**

Used to target **exactly one unique** element on the page.

### 🧪 Example:

```html
<h1 id="main-title">My Website</h1>
```

```css
#main-title {   
	color: green;   
	text-align: center; }
```

⚠️ Only **one element** should have a specific ID!

---

## 🟣 4. **Pseudo-Class Selectors (`:hover`, `:active`, `:focus`)**

These apply styles based on **user interaction** or **element state**.

### 🧪 Example:

```html
<a href="#">Hover over me</a>
```

```css
a {   
	color: blue;   
	text-decoration: none; }  
a:hover {   
	color: red;   
	text-decoration: underline; }
```

🎯 Common pseudo-classes:

|Selector|What it does|
|---|---|
|`:hover`|When mouse hovers over the element|
|`:active`|When the element is being clicked|
|`:focus`|When the element is focused (e.g., input)|

---

## 🧾 Summary Table

|Selector Type|Syntax|Targets|
|---|---|---|
|Tag Name|`p`, `h1`|All elements of that tag|
|Class Selector|`.classname`|All elements with that class|
|ID Selector|`#idname`|Only the element with that specific ID|
|Pseudo-class|`a:hover`|Specific states or interactions|

---
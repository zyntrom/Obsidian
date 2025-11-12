## 📦 What is Flexbox?

- **Flexbox (Flexible Box)** is a CSS layout model that helps arrange items **in one direction** — either row or column.
- Great for **responsive**, **neatly aligned**, and **evenly spaced** layouts.

> Think of it like arranging books or buttons on a shelf that can stretch, shrink, or align smartly.

---

## 🧱 1. Creating a Flex Container

Make any element a flex container using:

```css
.container {   display: flex; /* or inline-flex */ }
```

Inside, **child elements** become flex items.

---

## 🔄 2. `flex-direction`: Main Axis Control

Defines **direction** of items inside the container.

css

CopyEdit

```css
.container {   
	flex-direction: row;         /* default: left to right */   
	flex-direction: row-reverse; /* right to left */   
	flex-direction: column;      /* top to bottom */   
	flex-direction: column-reverse; /* bottom to top */ 
	}
```

🧭 Main axis = Direction of flow  
🕸️ Cross axis = Perpendicular to main axis

---

## 🧍 3. `justify-content`: Align Items Along Main Axis

Controls **horizontal alignment** when `flex-direction: row` (default).

css

CopyEdit

```css
.container {   
justify-content: flex-start;    /* default */   
justify-content: flex-end;   
justify-content: center;   
justify-content: space-between;   
justify-content: space-around;   
justify-content: space-evenly; }
```

🧠 Use for spacing: evenly, centered, pushed to sides, etc.

---

## 🧘 4. `align-items`: Align Items Along Cross Axis

Controls **vertical alignment** when `flex-direction: row`.

css

CopyEdit

```css
.container {   
align-items: stretch;      /* default - fills container */   
align-items: flex-start;   /* top */   
align-items: flex-end;     /* bottom */   
align-items: center;       /* center vertically */   
align-items: baseline;     /* aligns text baselines */ }
```

---

## ✍️ Example

```html
<div class="container">   
	<div class="item">A</div>   
	<div class="item">B</div>   
	<div class="item">C</div>
</div>
```

```css
.container {   
	display: flex;   
	flex-direction: row;   
	justify-content: space-around;   
	align-items: center; } 
.item {   
	padding: 20px;   
	background: lightblue; }
```

---

## ✅ Summary

| Property          | Purpose                                  |
| ----------------- | ---------------------------------------- |
| `display: flex`   | Turns element into a Flex container      |
| `flex-direction`  | Sets main axis direction (row/column)    |
| `justify-content` | Aligns items along main axis (spacing)   |
| `align-items`     | Aligns items along cross axis (vertical) |
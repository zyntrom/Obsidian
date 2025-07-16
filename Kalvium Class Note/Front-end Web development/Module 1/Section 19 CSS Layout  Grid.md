## 🧱 What is CSS Grid?

CSS Grid is a **two-dimensional layout system** in CSS, allowing you to manage **rows and columns** simultaneously — unlike Flexbox, which handles one direction at a time.

Use Grid when you need **precise control** over both horizontal and vertical layout.

---

## 🎯 Learning Objectives

- Understand the **CSS Grid system**
- Define **rows** and **columns**
- **Place** items using lines or area names
- Create **responsive layouts**
- Use **gap**, `minmax()`, and `auto-fit` effectively

---

## 📦 Creating a Grid Container

Make any element a grid container:

```css
.container {   
	display: grid; }
```

---

## 📐 Defining Columns & Rows

### ✅ `grid-template-columns`

```css
.container {   
	grid-template-columns: 100px 200px 1fr; }
```

- `100px`: Fixed
- `200px`: Fixed
- `1fr`: Remaining flexible space

### ✅ `grid-template-rows`

```css
.container {   
	grid-template-rows: 150px auto 1fr; }
```

---

## 🎯 Placing Grid Items

### Method 1: Grid Line Numbers

```css
.item1 {   
	grid-column-start: 1;   
	grid-column-end: 3;   
	grid-row-start: 1;   
	grid-row-end: 2; }
```

- Spans 2 columns (1 to 3)
- Spans 1 row (1 to 2)

---

### Method 2: Grid Template Areas

#### ✅ Define layout visually

```css
.container {   
	display: grid;   
	grid-template-columns: repeat(3, 1fr);   
	grid-template-rows: auto 1fr auto;   
	grid-template-areas:     "header header header"     "sidebar content content"     "footer footer footer";   
	gap: 10px; }
```

#### ✅ Assign area names

```css
header { 
	grid-area: header; } 
sidebar { 
	grid-area: sidebar; } 
content { 
	grid-area: content; } 
footer { 
	grid-area: footer; }
```

---

## ✨ Grid Gap

Add spacing between rows and columns:

```css
.container {   
	grid-gap: 20px; 
	row-gap: 20px; 
	column-gap: 10px;
	}
```

---

## 📱 Responsive Grid with `minmax()` and `auto-fit`

```css
.container {   
	display: grid;   
	grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));   
	grid-gap: 20px; }
```

- `minmax(200px, 1fr)`: Columns are at least 200px but can grow
- `auto-fit`: Adjusts number of columns based on space

---

## ✅ Summary

| Feature                 | Description                     |
| ----------------------- | ------------------------------- |
| `display: grid`         | Enables grid layout             |
| `grid-template-columns` | Defines column sizes            |
| `grid-template-rows`    | Defines row sizes               |
| Grid lines              | Use start/end to span areas     |
| Template areas          | Visual naming of layout parts   |
| `gap`, `row-gap`        | Adds spacing between grid items |
| `auto-fit`, `minmax()`  | Enables responsive behavior     |
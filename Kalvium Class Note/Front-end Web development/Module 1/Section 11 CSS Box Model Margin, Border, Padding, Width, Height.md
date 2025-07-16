## 🎯 Learning Objectives

- Understand the **CSS box model**
- Use **margin**, **padding**, and **border** to space and style elements
- Control element dimensions using **width** and **height**
- Visualize how all parts of a box add up in layout

---

## 📦 What is the CSS Box Model?

Each HTML element is a _rectangle box_ made of 4 parts:

`| Margin |   ← Outside spacing | Border |   ← Visible outline | Padding | ← Inside spacing | Content | ← Actual text or media`

Think of it like:

> 🖼️ Picture → **Image = content**, **Mat = padding**, **Frame = border**, **Wall gap = margin**

---

## 🟠 **Margin** – Outside Space

Adds space _outside_ the border — keeps distance from other elements.

```css
.box {   
	margin-top: 20px;   
	margin-right: 30px;   
	margin-bottom: 15px;   
	margin-left: 25px; }
```
🔹 Shorthand:
```css
margin: 20px 30px 15px 25px; /* top right bottom left /
```

---

## 🔵 **Border** – Visible Outline

Draws a line around the element (outside padding).

```css
.box {   
	border-width: 3px;  
	border-style: solid;   
	border-color: black; }
```

🎨 **Styles**: `solid`, `dashed`, `dotted`, `double`, `ridge`, `groove`

Custom sides:

```css
.box {   
	border-top: 2px dashed red;   
	border-bottom: 3px dotted blue; }
```

---

## 🟢 **Padding** – Inside Space

Creates space between content and border (inside the box).

```css
.box {   
	padding-top: 10px;   
	padding-right: 15px;   
	padding-bottom: 10px;   
	padding-left: 15px; }
```

🔹 Shorthand: `padding: 10px 15px;` (top-bottom, left-right)

---

## ⚙️ **Width & Height** – Content Size

Controls only the content area size (not padding, border, or margin).

```css
.box {   
	width: 200px;   
	height: 100px; }
```

📱 Responsive:

```css
.box {   
	width: 50%;   
	height: 30vh; }

```
---

## 📐 Box Size Formula

**Total size** of the element =  
`width + padding (L+R) + border (L+R) + margin (L+R)`

### Example:

```css
.box {   
	width: 200px;   
	height: 100px;   
	padding: 20px;   
	border: 5px solid;   
	margin: 30px; }
```

**Total Width** = 200 (content) + 40 (padding) + 10 (border) + 60 (margin) = `310px`  
**Total Height** = 100 (content) + 40 (padding) + 10 (border) + 60 (margin) = `210px`

---

## ✅ Summary

|Property|What it does|
|---|---|
|Margin|Outer space (element to element)|
|Border|Visible frame around element|
|Padding|Inner space (content to border)|
|Width|Sets width of content area|
|Height|Sets height of content area|

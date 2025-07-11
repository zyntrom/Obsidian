## 📱 What is Responsive Web Design?

Responsive web design means building a **single website** that:

- **Adapts automatically** to any screen size or orientation
- Works on **mobile, tablet, desktop**, etc.
- Provides a **great user experience** everywhere

**Benefits:**  
✅ Mobile-friendly  
✅ SEO boost  
✅ Easy maintenance  
✅ Wider audience reach

---

## 🎯 Learning Objectives

- Understand **responsive design**
- Use **media queries** to apply styles conditionally
- Create layouts that **adapt across screen sizes**
- Debug and test for **multiple devices**

---

## 🧪 What Are Media Queries?

Media queries let you apply CSS **only when specific conditions are met** (like screen width).

### 🔹 Syntax

```css
@media (condition) {   /* CSS styles here */ }
```
### 🔹 Example

```css
body {   font-size: 16px; }  @media (max-width: 600px) {   body {     font-size: 14px;   } }
```

If the screen is **≤ 600px**, font becomes **14px**.

---

## 📏 Common Media Query Conditions

|Condition|Description|
|---|---|
|`max-width`|Applies **up to** a certain width|
|`min-width`|Applies **from** a certain width|
|`max-height`/`min-height`|Based on **height**|
|`orientation`|Detects **landscape/portrait** mode|

---

## 🧩 Examples

### ✅ `max-width`

```css
@media (max-width: 768px) {   .container {     width: 100%;   } }
```

Used for small screens like phones/tablets.

---

### ✅ `min-width`

css

CopyEdit

```css
@media (min-width: 992px) {   .menu {     display: block;   } }
```

Used for larger screens like desktops.

---

### ✅ `orientation`

```css
@media (orientation: landscape) {   .box {     width: 300px;   } }
```

Adapts layout based on phone/tablet orientation.

---

## 🧪 Hands-On Example: Responsive Navbar

### 🔸 HTML

```css
<nav>   
<a href="#" class="logo">My Website</a>   
<ul class="menu">     
<li><a href="#">Home</a>
</li>    
</ul> 
</nav>
```

### 🔸 CSS

```css
nav {   
	display: flex;   
	justify-content: space-between; }  
@media (max-width: 768px) {   
nav {     
		flex-direction: column;   }   
.menu {     
	flex-direction: column;     
	width: 100%;   } }
```

**➡️ On desktop**: Horizontal  
**➡️ On mobile**: Vertical stacking

---

## 🧪 Debugging & Testing Tips

- Use **DevTools (F12)** → Responsive mode
    
- Try **emulators** or real devices
    
- Tools:  
    🔗 [Responsinator](https://www.responsinator.com/)  
    🔗 [BrowserStack](https://www.browserstack.com/)
    

---

## ✅ Summary

| Topic             | What You Learned                              |
| ----------------- | --------------------------------------------- |
| Responsive Design | Adapts to any screen                          |
| Media Queries     | Conditional CSS based on device properties    |
| Key Properties    | `min-width`, `max-width`, `orientation`, etc. |
| ANavbar Example   | Responsive menus with Flexbox & media queries |
## 📍 CSS Positioning

### 🎯 Learning Objectives:

- Understand types of CSS positioning
- Learn how they affect layout behavior
- Control layout and overlapping using `z-index`
- Apply practical layout patterns using positioning

---

### 📦 What is CSS Positioning?

CSS positioning determines **where and how elements appear** on the screen.  
It gives you **fine-grained control** over layout, movement, and stacking order.

---

### 🧱 Types of Positioning in CSS

|Type|Behavior|
|---|---|
|`static`|Default; elements flow normally, can't use `top`, `left`, etc.|
|`relative`|Moves element **relative to its normal position** (without affecting others)|
|`absolute`|Positions element **relative to nearest positioned ancestor** (removed from flow)|
|`fixed`|Positions element **relative to the screen**, stays fixed on scroll|
|`sticky`|Behaves like `relative` **until scroll threshold**, then becomes `fixed`|

---

### 💡 Examples:

#### Static (Default)

`div {   position: static; }`

#### Relative

`div {   position: relative;   top: 20px;   left: 10px; }`

#### Absolute

`.container {   position: relative; }  .child {   position: absolute;   top: 50px;   left: 0; }`

#### Fixed

`.footer {   position: fixed;   bottom: 0;   width: 100%; }`

#### Sticky

`.header {   position: sticky;   top: 0;   background: lightblue; }`

---

### 🧊 `z-index`: Layering Elements

- `z-index` controls which element appears **on top** when they overlap.
- Only works on **positioned elements** (`relative`, `absolute`, `fixed`, `sticky`)

`.box1 {   position: absolute;   z-index: 2; }  .box2 {   position: absolute;   z-index: 1; }`

> 🔺 Higher `z-index` = closer to viewer  
> 🔻 Lower `z-index` = behind other elements

---

### ✅ Summary

| Property   | Use Case                                       |
| ---------- | ---------------------------------------------- |
| `static`   | Normal page flow                               |
| `relative` | Small nudges / container for absolute elements |
| `absolute` | Exact placement within a relative parent       |
| `fixed`    | Sticky footers, headers, floating buttons      |
| `sticky`   | Sticky section headers, nav bars               |
| `z-index`  | Control overlapping of elements                |
![[Pasted image 20250710122250.png]]

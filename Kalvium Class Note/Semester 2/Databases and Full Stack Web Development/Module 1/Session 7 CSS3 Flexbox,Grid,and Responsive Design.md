# **Kalvium AL 1.7 — CSS3: Flexbox, Grid, and Responsive Design**

---

## **1. Introduction: Modern CSS Layouts**

Modern CSS layout systems — **Flexbox** and **Grid** — allow developers to create responsive, adaptive, and structured web page layouts efficiently.  
They eliminate the need for outdated techniques such as floats, tables, and manual positioning.

### **Why These Are Important**

|Aspect|Why It Matters|
|---|---|
|**Career Requirement**|Every front-end role expects knowledge of Flexbox and Grid.|
|**Mobile-First Design**|60%+ of web traffic is from mobile — responsive layouts are essential.|
|**Efficiency**|Build complex layouts quickly with fewer lines of CSS.|
|**Future-Proof**|Supported by all modern browsers and part of the CSS standard.|

---

## **2. The CSS Box Model**

Every HTML element is treated as a rectangular **box** in CSS.  
Understanding how the box is sized is crucial for layout design.

### **Box Components**

1. **Content** – The actual text or image inside the box.
2. **Padding** – Space between content and border.
3. **Border** – Surrounds the padding and content.
4. **Margin** – Space outside the border (between elements).

### **Two Box-Sizing Modes**

#### **(a) content-box (default)**

- The `width` and `height` apply only to the content.
- Padding and border are added _on top_ of the set width.

```css
.content-box {
  box-sizing: content-box;
  width: 200px;
  padding: 20px;
  border: 5px solid black;
  /* Total width = 200 + 40 + 10 = 250px */
}
```

#### **(b) border-box (recommended)**

- The `width` and `height` include content, padding, and border.
- Easier to calculate total element size.

```css
.border-box {
  box-sizing: border-box;
  width: 200px;
  padding: 20px;
  border: 5px solid black;
  /* Total width = 200px exactly */
}
```

#### **Global Reset (Best Practice)**

```css
* {   box-sizing: border-box; }
```

---

## **3. Flexbox: One-Dimensional Layout System**

**Flexbox (Flexible Box Layout)** organizes items along **a single axis** — either a row or a column.

### **Creating a Flex Container**

```css
.container {   display: flex; }
```
→ All direct children of `.container` become **flex items**.

---

### **Core Flexbox Properties**

#### **(1) flex-direction**

Defines the main axis direction.

|Value|Layout Direction|
|---|---|
|`row`|Left → Right (default)|
|`row-reverse`|Right → Left|
|`column`|Top → Bottom|
|`column-reverse`|Bottom → Top|

```css
.container {   flex-direction: row; }
```

---

#### **(2) justify-content**

Controls alignment along the **main axis** (horizontal by default).

|Value|Description|
|---|---|
|`flex-start`|Items start at left|
|`center`|Centered horizontally|
|`flex-end`|Items align to right|
|`space-between`|Equal spacing, no edges|
|`space-around`|Even gaps, half-space at edges|
|`space-evenly`|Perfectly equal spacing everywhere|

```css
.container {   justify-content: space-between; }
```

---

#### **(3) align-items**

Controls alignment along the **cross axis** (vertical by default).

|Value|Description|
|---|---|
|`stretch`|Default — fills container height|
|`flex-start`|Aligns to top|
|`center`|Vertically centers items|
|`flex-end`|Aligns to bottom|
|`baseline`|Aligns text baselines|

```css
.container {   align-items: center; }
```

---

#### **(4) gap**

Adds consistent space between flex items.

```css
.container {   display: flex;   gap: 1rem; }
```

---

#### **(5) flex**

Defines how items grow or shrink relative to available space.

```css
.card {   flex: 1; /* Equal width cards */ }
```

---

### **Common Flexbox Layout Patterns**

#### **Centered Content (Perfect Center)**

```css
.center {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

```

#### **Navigation Bar**

```css
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 2rem;
}
```

#### **Equal Width Cards**

```css
.card-container {
  display: flex;
  gap: 1rem;
}
.card {
  flex: 1;
}

```
---

## **4. CSS Grid: Two-Dimensional Layout System**

**Grid Layout** provides control in **two directions — rows and columns.**

### **Creating a Grid Container**

```css
.grid-container {
  display: grid;
}
```

---

### **Core Grid Properties**

#### **(1) grid-template-columns**

Defines how many and how wide columns are.

```css
/* 3 equal columns */
grid-template-columns: repeat(3, 1fr);

/* Different column sizes */
grid-template-columns: 200px 1fr 2fr;

/* Responsive columns */
grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));

```

**`fr` (fraction unit)** → divides available space proportionally.

---

#### **(2) grid-template-rows**

Defines row heights.

```css
grid-template-rows: 100px auto 50px;
```

---

#### **(3) gap / row-gap / column-gap**

Adds space between grid cells.

```css
gap: 20px;  /* both rows & columns */
```

---

### **Common Grid Patterns**

#### **Photo Gallery**

```css
.gallery {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1rem;
}

```

#### **Dashboard Layout**

```css
.dashboard {
  display: grid;
  grid-template-columns: 250px 1fr;
  grid-template-rows: 60px 1fr 40px;
  gap: 1rem;
  height: 100vh;
}
```
#### **Card Grid (with large card)**

```css
.card-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 1rem;
}

.card-large {
  grid-column: span 2;
  grid-row: span 2;
}
```

---

## **5. Responsive Design**

Responsive Design ensures websites look good across all screen sizes.

### **Core Principle: Mobile-First**

Start with styles for **small screens**, then expand for larger screens using **media queries**.

---

### **Media Query Syntax**

```css
@media (min-width: 768px) {   
	/* Styles for screens wider than 768px */ 
}
```
### **Example: Responsive Container**

```css
/* Base (mobile) */
.container {
  display: flex;
  flex-direction: column;
  padding: 1rem;
}

/* Tablet and up */
@media (min-width: 768px) {
  .container {
    flex-direction: row;
    padding: 2rem;
  }
}

/* Desktop and up */
@media (min-width: 1024px) {
  .container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 3rem;
  }
}
```

---

### **Common Breakpoints**

|Device|Width Range|Layout Behavior|
|---|---|---|
|**Mobile**|< 768px|Single column, stacked layout|
|**Tablet**|768–1023px|Two columns, simplified nav|
|**Desktop**|1024px+|Full multi-column layout|
|**Large Desktop**|1440px+|Wide layouts with max-width container|

---

### **Responsive Grid Example**

`.grid {   display: grid;   grid-template-columns: 1fr;   gap: 1rem; }  @media (min-width: 768px) {   .grid {     grid-template-columns: repeat(2, 1fr);   } }  @media (min-width: 1024px) {   .grid {     grid-template-columns: repeat(3, 1fr);   } }`

---

## **6. Flexbox vs Grid: Comparison Table**

|Use Flexbox When...|Use Grid When...|
|---|---|
|Layout flows in **one direction**|Layout needs **rows and columns**|
|Ideal for navbars, toolbars, footers|Ideal for dashboards, galleries, complex pages|
|Good for **alignment and centering**|Good for **precise structure and placement**|
|Content size is variable|Fixed, uniform grid patterns|
|Easier for small components|Better for full-page layouts|

✅ **Best Practice:** Combine both — use Grid for page layout and Flexbox for elements _inside_ each grid area.

---

## **7. Summary & Quick Reference**

### **Flexbox Properties**

- `display: flex`
    
- `flex-direction`
    
- `justify-content`
    
- `align-items`
    
- `align-content`
    
- `gap`
    
- `flex: grow shrink basis`
    

### **Grid Properties**

- `display: grid`
    
- `grid-template-columns`
    
- `grid-template-rows`
    
- `gap / row-gap / column-gap`
    
- `grid-column`, `grid-row`
    

### **Responsive Design**

- Use `@media (min-width: …)` queries.
    
- Always start **mobile-first**.
    
- Test at all major breakpoints.
    

---

✅ **Exam Key Points to Remember**

- **Flexbox:** One-dimensional layout → `justify-content` (main axis) and `align-items` (cross axis).
    
- **Grid:** Two-dimensional → rows and columns.
    
- **border-box** is preferred for easier sizing.
    
- Always verify with browser resizing.
    
- Combine Grid + Flexbox for optimal responsive design.
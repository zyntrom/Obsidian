## 🎨 Scenario: Styling the CodeCrust Homepage

You already built the HTML structure.  
Now, you bring the page to life with layout, color, spacing, and **responsiveness** using modern CSS tools: **Flexbox**, **Grid**, and **Media Queries**.

---

## 🎯 Goals of This Phase

✔ Use **Flexbox** and **Grid** to arrange content  
✔ Style headings, buttons, forms, and layout boxes  
✔ Use **media queries** for responsive design  
✔ Add colors, fonts, spacing, and interactive hover effects  
✔ Use **relative units** for flexible, scalable layout

---

## 💡 Key CSS Concepts & Snippets

### 1️⃣ Flexbox for Navigation & Testimonials

css

CopyEdit

`nav {   display: flex;   justify-content: space-between;   align-items: center; }  .testimonials {   display: flex;   gap: 1.5rem; }`

---

### 2️⃣ Grid for Pizza Menu Section

css

CopyEdit

`.menu {   display: grid;   grid-template-columns: repeat(3, 1fr);  /* 3 equal columns */   gap: 20px; }`

---

### 3️⃣ Responsive Design (Media Queries)

Make your layout mobile-friendly:

css

CopyEdit

`@media (max-width: 768px) {   .menu {     grid-template-columns: 1fr;  /* Stack pizzas vertically */   }    .testimonials {     flex-direction: column;   }    nav {     flex-direction: column;     align-items: flex-start;   } }`

---

### 4️⃣ Typography

css

CopyEdit

`body {   font-family: 'Poppins', sans-serif;   color: #333;   line-height: 1.6; }`

---

### 5️⃣ Spacing and Box Styling

css

CopyEdit

`.card {   padding: 16px;   margin-bottom: 20px;   border-radius: 10px;   background-color: #fefefe; }`

---

### 6️⃣ Brand Theme & Color Palette

css

CopyEdit

`.header {   background-color: #111;   color: #fff; }`

---

### 7️⃣ Hover Effects and Transitions

css

CopyEdit

`.btn {   background-color: #ff5500;   color: white;   padding: 12px 24px;   border-radius: 5px;   border: none; }  .btn:hover {   background-color: #ff7700;   transition: background-color 0.3s ease; }`

---

### 8️⃣ Responsive Units

css

CopyEdit

`.container {   max-width: 90vw;   padding: 2rem; }`

---

### 9️⃣ Z-Index & Absolute Positioning

css

CopyEdit

`.hero-text {   position: absolute;   top: 50px;   left: 30px;   z-index: 10; }`

---

## ✅ Summary

| Feature               | Description                                    |
| --------------------- | ---------------------------------------------- |
| Flexbox               | Used for navigation and horizontal layouts     |
| Grid                  | Used for multi-column pizza/menu layout        |
| Media Queries         | Mobile-friendly stacking and responsive design |
| Fonts/Colors          | Custom font, bold palette for brand identity   |
| Spacing & Padding     | Controlled with rem/px and border-radius       |
| Hover Effects         | Interactive buttons with transitions           |
| Units                 | `%`, `vw`, `rem` for flexible layouts          |
| Positioning & Z-Index | Layering content with `absolute`, `z-index`    |
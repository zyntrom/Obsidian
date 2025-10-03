# 📒 6.2 Styling React Components: CSS Modules / Basic Styling

---

## 🔹 Overview

Styling in React is about **making your components visually appealing**. Components are like building blocks—you can build an app, but styling makes it engaging and user-friendly.

---

## 🔹 Learning Objectives

By the end of this lesson, you should be able to:

1. Understand different approaches to styling React components
2. Use **basic CSS** with React components
3. Use **CSS Modules** for scoped styles
4. Apply styling techniques to create reusable, visually appealing components

---

## 🔹 Why Styling is Important

|Reason|Benefit|
|---|---|
|User Experience|Makes app enjoyable to use|
|Brand Identity|Consistent styling reinforces brand|
|Accessibility|Improves usability for users with disabilities|
|Visual Hierarchy|Guides user's eye to important elements|

---

## 🔹 Styling Techniques in React

### 1️⃣ Basic CSS

- Create a CSS file (`my-component.css`) and define styles.
- Import it into your component:

```js
import './my-component.css';

function MyComponent() {
  return (
    <div className="my-component">
      <h1>Hello, Styled Component!</h1>
      <p>This is styled using basic CSS.</p>
    </div>
  );
}

```

**Note:** Styles are **global** and may affect other components with same class names.

---

### 2️⃣ Inline Styles

- Define styles as a **JavaScript object** and apply via `style` attribute:

```js
const myStyle = {
  backgroundColor: 'lightblue',
  padding: '10px',
  color: 'navy'
};

<div style={myStyle}>Hello!</div>

```

**Use:** Dynamic styles depending on state or props. Only affects that element.

---

### 3️⃣ CSS Modules

- Scoped CSS to avoid naming collisions.
    
- File extension: `.module.css` (e.g., `my-component.module.css`)
    

```
import styles from './my-component.module.css';

<div className={styles.myComponent}>
  Hello!
</div>

```

**Benefits:**

- Styles are **scoped locally**
    
- Automatically generates **unique class names**
    

---

### 4️⃣ Styled Components (CSS-in-JS)

- Write CSS directly in JavaScript using **tagged template literals**.
    
- Install via: `npm install styled-components`
    

``import styled from 'styled-components';  const StyledButton = styled.button`   background-color: #4CAF50;   color: white;   padding: 15px 32px;   &:hover {     background-color: #3e8e41;   } `;  <StyledButton>Click Me</StyledButton>``

**Benefits:**

- Encapsulates styles inside components
    
- Great for dynamic styles and reusable components
    

---

## 🔹 When to Use Which Technique

|Technique|Use Case|
|---|---|
|Basic CSS|Small projects, global styles|
|Inline Styles|Dynamic styles based on state/props|
|CSS Modules|Large projects, avoid naming collisions|
|Styled Components|CSS-in-JS, dynamic styling, reusable components|

---

## 🔹 Common Pitfalls

- **Naming Collisions:** Use CSS Modules / Styled Components
    
- **Specificity Issues:** Avoid overly generic selectors; consider Sass
    
- **Performance:** Avoid excessive inline styles
    

---

## 🔹 Real-World Example: Button Component

**CSS Module (`button.module.css`)**:

`.button {   background-color: #4CAF50;   color: white;   padding: 15px 32px; } .button:hover {   background-color: #3e8e41; }`

**Button Component (`Button.js`)**:

`import styles from './button.module.css';  function Button({ children, onClick }) {   return <button className={styles.button} onClick={onClick}>{children}</button>; }`

- Reusable button with **hover effect** and **consistent styling**.
    

---

## 🔹 Additional Resources

- React Official Documentation – Styling
    
- [CSS Modules Documentation](https://github.com/css-modules/css-modules)
    
- Styled Components Documentation
    

---

## 🔹 Summary

- **Basic CSS:** Global styles using `.css` files
    
- **Inline Styles:** Element-specific, dynamic styles
    
- **CSS Modules:** Scoped, component-level CSS
    
- **Styled Components:** CSS-in-JS, reusable and dynamic
# 🌟 Conditional Rendering in React

## 🚀 What is Conditional Rendering?

- Conditional rendering = showing **different UI** based on **state** or **props**.
- Example idea:
    
    - If `isLoggedIn = true` → show Dashboard.
    - Else → show Login form.

---

## ⚡ Ways to Do Conditional Rendering in React

### 1. **if / else statement**

- Used outside the `return`.
- Good for **long / complex logic**.

Example: Login Toggle

- Track `isLoggedIn` using `useState`.
- If true → render Welcome Message.
- If false → render Login Button.

👉 Try:

- Change default to `true`.
- Add a Logout button that resets `isLoggedIn` to `false`.

---

### 2. **Ternary Operator (`? :`)**

- Syntax: `condition ? <A /> : <B />`
- Cleaner and shorter than if/else.
- Use directly inside JSX.

---

### 3. **Logical AND (`&&`)**

- Syntax: `condition && <Component />`
- Shows a component **only if the condition is true**.
- Nothing is shown if false.

---

## 📌 When to Use Which?

|Approach|Best Use Case|
|---|---|
|**if/else outside return**|Long / complex logic|
|**Ternary in JSX**|Short, simple checks|
|**&& operator**|Show one thing if condition is true|

---

## 🛠 Practice Ideas

- **Admin Panel** → Show _“Welcome Admin”_ if `isAdmin = true`, else _“Access Denied”_.
- **Dark Mode Toggle** → Button switches between Dark & Light Mode.
- **Cart Message** → If `items.length === 0`, show _“Your cart is empty”_, else show cart contents.
- 
```embed
title: "Conditional Rendering Components in React"
image: "https://i.ytimg.com/vi/xRKvjWDZlW8/maxresdefault.jpg"
description: "Learn how conditionally render components using conditional ternary (? : ) and logical and (&&) operators, and if else statements. This is video #9 in my rea..."
url: "https://youtu.be/xRKvjWDZlW8"
favicon: ""
aspectRatio: "56.25"
```

---

## 🎯 Summary

✅ Conditional rendering = control UI output using logic.  
✅ Three main tools: **if/else**, **ternary**, **&&**.  
✅ Based on **state** or **props**.  
✅ Practice with real UI cases (login, toggles, modals).
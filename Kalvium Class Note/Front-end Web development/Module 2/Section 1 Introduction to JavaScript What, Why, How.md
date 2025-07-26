## 📘 JavaScript Fundamentals – Lesson 1: Introduction to JavaScript

### 🎯 Learning Objectives

- Understand what JavaScript is.
- Know why JavaScript is used in web development.
- Learn how to embed JS in HTML.
- Make web pages interactive using JS.

---

### 🧠 What is JavaScript?

- A **scripting language** that makes web pages dynamic and interactive.
- Runs **in the browser**.
- Examples: Pop-ups, form validation, sliders, games, real-time content.

**Think:**

- HTML → Structure
- CSS → Style
- JavaScript → Behavior

---

### 💡 Why Use JavaScript?

- Reacts to **user actions** (click, type, scroll).
- Enables **live updates** (e.g., search suggestions).
- Adds **intelligence** to pages (form validation, content change, animations).
- Without JS = static page  
    With JS = interactive experience
    

---

### ⚙️ How Does JavaScript Work?

- Embedded using `<script>` tags.
    
- Can be written:
    
    - **Inline** (inside HTML)
        
    - **Externally** (`.js` file linked to HTML)
        
- Waits for events → runs specific **functions** in response.
    

---

### 🧾 Basic Syntax

javascript

CopyEdit

`// This is a comment let message = "Hello, Kalvians!"; alert(message);`

- `let` → declares a variable
    
- `alert()` → shows a popup with the variable content
    
- Think of:
    
    - **Variables** = containers for data
        
    - **Functions** = actions you can perform
        

---

### 🧩 Embedding JS in HTML

html

CopyEdit

`<!DOCTYPE html> <html> <head>     <title>My First JavaScript</title> </head> <body>     <h1>Hello, Kalvians!</h1>     <script>         alert("Welcome to JavaScript!");     </script> </body> </html>`

- `<script>` tag runs JavaScript code.
    
- Place it **at the end of `<body>`** so HTML loads first.
    

---

### 🖱️ Making Web Pages Interactive

html

CopyEdit

`<!DOCTYPE html> <html> <head>     <title>Interactive JavaScript</title> </head> <body>     <button onclick="showMessage()">Click Me!</button>     <script>         function showMessage() {             alert("Button Clicked!");         }     </script> </body> </html>`

- `onclick` → event attribute that triggers a function.
    
- `showMessage()` → user-defined function to handle the click.
    
- **Event Listener** → JS listens for an event and reacts.
    

---

### ✅ Summary

- **What**: JS = Language for interactivity.
    
- **Why**: To make responsive, engaging web pages.
    
- **How**: Use `<script>`, define functions, and respond to events.
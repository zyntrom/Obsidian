# 🧠 Kalvium AL — 1.32 Dynamic UI with Vanilla JS

---

## 🎯 **Introduction: Building Interactivity Without a Framework**

Frameworks like **React** simplify UI creation, but understanding the **core JavaScript (Vanilla JS)** principles behind them is essential.  
In this lesson, we’ll build a **modal (popup)** window from scratch using only **HTML**, **CSS**, and **JavaScript**, exploring **DOM manipulation**, **event handling**, and **class-based state toggling**.

---

## 🧩 **Core Question: How Does a Popup Work?**

A modal involves three layers working together:

|Part|Technology|Role|
|---|---|---|
|**Structure**|HTML|Defines elements like button, overlay, and modal window|
|**Appearance**|CSS|Controls visibility, layout, and style|
|**Behavior**|JS|Handles interactions and toggles visibility dynamically|

---

## 🧱 **Outcome 1: HTML Structure of the Modal**

### 📜 **Structure Blueprint**

`<!-- Trigger Button --> <button id="open-modal-btn">Open Modal</button>  <!-- Overlay (initially hidden) --> <div id="modal-overlay" class="modal-overlay">   <!-- Modal Window -->   <div class="modal">     <h2>This is a Modal Window</h2>     <p>You can put any content you want here.</p>     <button id="close-modal-btn">Close</button>   </div> </div>`

### 🧠 **Breakdown**

- **open-modal-btn:** Button to trigger the modal.
    
- **modal-overlay:** Dimmed background overlay.
    
- **modal:** The popup box containing the content.
    

---

## 🎨 **Outcome 2: Styling and Hiding the Modal with CSS**

### 🌑 Overlay Style

`.modal-overlay {   display: none; /* Hidden by default */   position: fixed;   top: 0; left: 0;   width: 100%; height: 100%;   background-color: rgba(0, 0, 0, 0.5);   display: flex;   justify-content: center;   align-items: center; }`

### 📦 Modal Box

`.modal {   background-color: white;   padding: 20px;   border-radius: 5px;   width: 500px;   max-width: 90%; }`

### 💡 Visibility Toggle Class

`.modal-overlay.is-visible {   display: flex; }`

🗝️ **Concept:**  
JavaScript won’t directly manipulate CSS properties — it will simply **add or remove** this `.is-visible` class to show or hide the modal.

---

## ⚙️ **Outcome 3: Showing the Modal (JavaScript)**

### 🔍 Step 1: Select Elements

`const openModalBtn = document.getElementById('open-modal-btn'); const modalOverlay = document.getElementById('modal-overlay');`

### 🖱️ Step 2: Add Click Event Listener

`openModalBtn.addEventListener('click', function() {   modalOverlay.classList.add('is-visible'); });`

✅ When the button is clicked, the overlay gets the `.is-visible` class — making it appear.

---

## ❌ **Outcome 4: Closing the Modal**

### 🔘 Step 1: Close Button

`const closeModalBtn = document.getElementById('close-modal-btn');  closeModalBtn.addEventListener('click', function() {   modalOverlay.classList.remove('is-visible'); });`

### 🖤 Step 2: Clicking the Overlay Background

`modalOverlay.addEventListener('click', function(event) {   if (event.target === modalOverlay) {     modalOverlay.classList.remove('is-visible');   } });`

🧠 **Why check `event.target === modalOverlay`?**  
To prevent **event bubbling** — without this, clicking _inside_ the modal would also close it unintentionally.

---

## 🧩 **Challenge: Accordion (FAQ) Toggle**

### 🏗️ HTML

`<h3>Frequently Asked Questions</h3> <div class="faq-item">   <div id="question1" class="question">What is Vanilla JS?</div>   <div id="answer1" class="answer hidden-answer">     It's plain JavaScript without any additional libraries or frameworks.   </div> </div>`

### 🎨 CSS

`.question {   cursor: pointer;   font-weight: bold;   background-color: #f0f0f0;   padding: 10px; } .hidden-answer { display: none; } .answer.is-visible {   display: block;   padding: 10px;   border: 1px solid #f0f0f0; }`

### ⚙️ JavaScript

`const question1 = document.getElementById('question1'); const answer1 = document.getElementById('answer1');  question1.addEventListener('click', function() {   answer1.classList.toggle('is-visible'); });`

✅ The `toggle()` method automatically adds or removes the `.is-visible` class each time you click.

---

## 🧠 **Knowledge Check**

|Question|Answer|
|---|---|
|**Does JS directly modify styles?**|No — it toggles CSS classes. CSS defines the styles for each state.|
|**Why check `event.target`?**|To prevent event bubbling so that clicks inside the modal don’t close it.|

---

## 💡 **Best Practices & Advanced Concepts**

- **Accessibility:** Use `aria-modal="true"` and trap focus inside modal for keyboard users.
    
- **CSS Transitions:** Add animations with `opacity` or `transform: scale()` for smoother effects.
    
- **State Management:** In React, this behavior translates to toggling `useState` values.
    
- **Separation of Concerns:**
    
    - JS → Controls _state_ (visible or hidden).
        
    - CSS → Controls _presentation_.
        

---

## 🏁 **Key Takeaways**

✅ Build UI components with **HTML (structure)**, **CSS (style)**, and **JS (behavior)**.  
✅ Use **DOM manipulation** (`getElementById`, `classList.add/remove/toggle`) for interactivity.  
✅ Avoid direct style manipulation — use **CSS classes** for cleaner code.  
✅ Prevent **event bubbling** with careful event handling.  
✅ These principles are the foundation of frameworks like **React**.
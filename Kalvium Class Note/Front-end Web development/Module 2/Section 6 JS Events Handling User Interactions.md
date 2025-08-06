### 📌 **Quick Revision Notes — JavaScript Events & Event Listeners**

#### ✅ **What are Events & Event Listeners?**

- **Event**: User actions like clicking, typing, loading a page.
- **Event Listener**: A method that _watches_ for an event.
- **Event Handler**: A function that runs when the event occurs.

👉 _Think of listeners as sensors that wait and react when something happens on the webpage._

---

### 🔧 **Using `addEventListener()`**

**Syntax:**

```js
element.addEventListener('eventType', handlerFunction);
```

#### 🔔 Example – Button Click

HTML:

```html
<button id="myButton">Click Me!</button>
```

JS:

```js
const button = document.getElementById('myButton'); button.addEventListener('click', function() {   
	alert('Button clicked!'); 
});
```

---

### 🧠 **Event Handler Functions**

- Run when event occurs.
- Can:
    - Change text/content
    - Change styles
    - Use the **event object** to get details (`event.target`, `event.key`, etc.)

Example:
```js
button.addEventListener('click', function(event) { 
	event.target.textContent = 'Clicked!'; 
});
```

---

### 🖱️ **Common Event Types**

#### 🔡 Keyboard (`keydown`)

```html
<input type="text" id="myInput" />
```

```js
input.addEventListener('keydown', function(event) {   console.log('Key pressed:', event.key); });
```

#### 🐭 Mouse (`mouseover` / `mouseout`)

```html
<div id="myDiv">Hover over me</div>
```

```js
div.addEventListener('mouseover', function() { 
	div.style.backgroundColor = 'yellow'; 
});  
div.addEventListener('mouseout', function() {   
	div.style.backgroundColor = 'white'; 
});
```

---

### 📚 **Summary**

- `addEventListener()` attaches events to DOM elements.
- Handlers define what should happen.
- Use the **event object** to get more info about the action.
- Combine with DOM manipulation to make **interactive** pages.
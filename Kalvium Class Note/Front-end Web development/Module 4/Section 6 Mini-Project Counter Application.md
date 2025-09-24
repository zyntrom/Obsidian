# Mini-Project: Counter Application (React Class Components)

## Why Class Components?

- Earlier React apps relied heavily on **class components** for state management.
- Functional components + Hooks (modern React) came later.
- This project steps back to **learn how things worked under the hood**:
    - State management
    - Event handling
    - Updating UI with `setState()`

---

## What You'll Build

A **simple counter app** that:

- Starts from **0**
- Lets you **increment (+)** and **decrement (–)** the counter using buttons
- Passes **all Jasmine test cases**

---

## Project Setup & Structure

```
.
├── src/
│   └── App.jsx         # Write your counter component here
├── test/
│   └── App.test.js     # Jasmine test cases (do not edit!)
├── README.md
├── package.json

```

### Commands

- `npm install` → Install dependencies
- `npm run dev` → Start dev server → view app at `http://localhost:5173`
- `npm run test:serve` → Run Jasmine test cases

---

## What You'll Learn

- **Creating and managing state** inside class components
- Handling **user interactions** with `onClick`
- Updating UI using **`this.setState()`**
- Running tests with Jasmine
- Basics of **Test-Driven Development (TDD)**

---

## Core Concepts

### 1. State in Class Components

- State is initialized inside the **constructor** or as a **class property**.
- Example:
```js
class Counter extends React.Component {   
	constructor(props) {     
		super(props);     
		this.state = { count: 0 };   
	} 
} 
```

### 2. Updating State

- Use **`this.setState()`** to update state (never modify directly).
- Example:
```js
this.setState({ count: this.state.count + 1 });
```

### 3. Event Handling

- Attach event handlers using `onClick`.
- Must use **arrow functions** or bind methods in the constructor.
- Example:
    
```js
increment = () => {   
	this.setState({ count: this.state.count + 1 }); 
}
```
    

### 4. Rendering UI

- Use **`render()` method** to define JSX.
    
- Example structure:
    
```js
render() {   
	return (     
		<div>       
			<button onClick={this.decrement}>–</button>       
			<span>{this.state.count}</span>       
			<button onClick={this.increment}>+</button>     
		</div>   
	); 
}
```
    

---

## Tests You Must Pass

1. ✅ Renders counter with initial value of **0**
2. ✅ Increments counter when **+ button** is clicked
3. ✅ Decrements counter when **– button** is clicked

Run with:

```
npm run test:serve
```

---

## Common Mistakes to Avoid

❌ Using a **function component** instead of a class → Tests expect class.  
❌ Forgetting `this.` before `state` or `setState`.  
❌ Not binding methods in constructor (if not using arrow functions).  
❌ Hardcoding values instead of reading from **state**.  
❌ Editing the **test file** (`App.test.js`).

---

## Checklist Before Submit

- ✅ UI renders with **+ , 0 , –**
- ✅ Uses **class component**
- ✅ Counter **increments/decrements correctly**
- ✅ All tests **pass**
- ✅ Code is **clean, readable, and commented**

---

## Key Takeaways

- **Class components** were the original way to manage state in React.
- **`this.state`** holds local component state.
- **`this.setState()`** updates state and re-renders UI.
- **Event handlers** must use arrow functions or binding.
- You just practiced:
    - **State management**
    - **Event handling**
    - **Test-driven coding (TDD)**
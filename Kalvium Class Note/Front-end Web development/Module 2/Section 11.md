## 🦖 Project 2: Building a Game with JavaScript – Part 1

### 🎮 Scenario

- No internet connection.
- Chrome's pixelated dinosaur game appears.
- Goal: **Recreate that game** using **HTML, CSS, and JavaScript**.
- In Part 1:
    - Create game layout (HTML).
    - Style the game (CSS).
    - Make the dinosaur jump (JavaScript).

---

### 🎯 Learning Objectives

By the end of this lesson, you will:

- Structure a basic game canvas using **HTML**.
- Style visual elements using **CSS**.
- Control game actions (jump) using **JavaScript**.
- Understand how **keyboard events** enable interactivity.

---

### 🧱 HTML Structure

```html
<div class="game">   
	<div id="dino" class="dino"></div>   
	<div class="ground"></div> 
</div>
```

**Explanation:**

- `.game`: Main container (the game area).
- `#dino` / `.dino`: Player (dinosaur).
- `.ground`: Ground line/floor.

---

### 🎨 CSS Styling

```css
.dino {   
	width: 50px;   
	height: 50px;   
	background-color: green;   
	position: absolute;   
	bottom: 0;   
	left: 50px; 
}
```
**Explanation:**

- `position: absolute`: Fixes dino at the bottom.
- `bottom: 0`: Dino rests on the ground.
- `left: 50px`: Horizontal position from left.
- `background-color`: Simple green box for now.

---

### 🕹️ JavaScript Jump Logic

```js
document.addEventListener('keydown', function () {
	dino.classList.add('jump');   
	setTimeout(() => dino.classList.remove('jump'), 500); 
});
```

**Explanation:**

- Listens for any **keyboard press**.
- Adds the `jump` class to animate the dino.
- Removes it after 500ms (animation duration).

---

### 🧑‍🔧 What You’ll Do (Implementation Plan)

#### ✅ 1. Create the Game Layout

- Create 3 `<div>`s:
    - `.game`
    - `#dino` / `.dino`
    - `.ground`

#### ✅ 2. Style the Dinosaur & Ground

- Use CSS:
    - `width`, `height`, `background-color`
    - `position: absolute`, `bottom`, `left`

#### ✅ 3. Implement the Jump Animation

- Add a `.jump` class in CSS using `@keyframes`
- Move the dino **up** and then **down**

```css
@keyframes jump {   
	0% { bottom: 0; }   
	50% { bottom: 100px; }   
	100% { bottom: 0; } 
}  
.jump {   
	animation: jump 0.5s ease; 
}
```

#### ✅ 4. Trigger the Jump with JavaScript

- On `keydown`, add `.jump` class
- Use `setTimeout` to remove `.jump` class after 0.5s

---

### 💡 Explanation

- The `.jump` class gives a **temporary bounce effect**.
- JavaScript **responds to user input** by changing CSS class.
- **CSS animations** handle the smooth visual movement.

---

### 📌 Summary

You have:

- ✅ Structured a basic game UI using **HTML**.
- ✅ Styled the dino and ground with **CSS**.
- ✅ Enabled the dino to jump with **JavaScript** and **CSS animations**.
- ✅ Linked **keyboard events** to game interactivity.
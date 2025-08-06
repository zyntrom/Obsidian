## 🕹️ _Project 2: Building a Game with JavaScript – Part 2_

**Frontend Web Development | SPE 2025**

---

### 🚨 Scenario

- Your dinosaur can now jump.
- Now it's time to add danger:
    - Create obstacles (like cacti).
    - Move them across the screen.
    - Detect collisions.
    - Show “Game Over” when dino hits obstacle.

---

### 🎯 Learning Objectives

By the end of this lesson, you will:

- Dynamically create elements using **JavaScript** (`createElement`)
- Animate objects using **`setInterval()`**
- Detect collision using **position comparison**
- Handle game over conditions with alerts or reloads

---

### 🧱 Dynamic Elements

**Creating obstacles (cactus, rock, etc.) using JS:**

```js
const obs = document.createElement('div'); obs.classList.add('obstacle'); game.appendChild(obs);
```

- `document.createElement('div')`: Makes a new `<div>`
- `.classList.add('obstacle')`: Adds styling class
- `game.appendChild(obs)`: Adds it inside the game area

---

### 🏃 Movement Logic

**Move obstacle to the left continuously:**

```js
let obsLeft = 1000;  setInterval(() => {   
	obsLeft -= 10;   
	obs.style.left = obsLeft + 'px'; }, 20);
```

- `obsLeft -= 10`: Moves obstacle 10px left every time
- `obs.style.left`: Updates its position on screen
- `setInterval(..., 20)`: Runs every 20ms → smooth animation

---

### 💥 Collision Detection

**Check if dino and obstacle overlap:**
```js
const dinoTop = parseInt(getComputedStyle(dino).getPropertyValue("bottom"));  
if (obsLeft < 100 && obsLeft > 50 && dinoTop < 50) {   alert("Game Over"); }
```

- `getComputedStyle(...)`: Gets CSS properties
    
- `bottom` value: How high the dino is
    
- If obstacle is in front of the dino **and** dino is low (not jumping), collision happens
    

---

### ✅ What You’ll Do

#### 1. **Create Obstacles Dynamically**

- Use `createElement()`
    
- Add class `obstacle`
    
- Append to game div using `appendChild()`
    

#### 2. **Animate Obstacle Movement**

- Use `setInterval()` to:
    
    - Decrease left position
        
    - Update `style.left`
        

#### 3. **Detect Collision**

- Use `getComputedStyle()` to get dino position
    
- Check if obstacle is within crash zone
    
- Check if dino is not jumping (i.e. low)
    

#### 4. **Trigger Game Over**

- On collision:
    
    - Show alert: `"Game Over"`
        
    - Optionally reload page or stop intervals
        

---

### 💡 Explanation

|Feature|How It Works|
|---|---|
|Motion|`setInterval()` changes `left` position|
|Collision|Compares dino's `bottom` & obstacle's `left`|
|Game Over|Triggered by logical condition + `alert()`|

---

### ✨ Summary

You have:

- 🚧 Created obstacles in JavaScript
    
- 🏃 Made them move across the screen
    
- 💥 Detected collision using positions
    
- ☠️ Shown Game Over and stopped the game
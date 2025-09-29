## 🦖 Project 2: Building a Game with JavaScript – Part 3

**Frontend Web Development | SPE 2025**

---

### 🎯 Objective

Make your Dino game **complete and polished** by adding:
- ✅ Real-time score counter
- ✅ Visual improvements
- ✅ Restart mechanism
- ✅ Clean layout using **only HTML, CSS, JS**

---

### 🛠️ What You’ll Build

A fully working Dino runner game with:
- 🦖 Jumping logic using keyboard
- 🌵 Moving obstacles that trigger Game Over
- 🧮 Auto-incrementing score
- 🔄 Clean restart on game over
- 🎨 Polished visuals with a modern layout

---

### 🧱 Step-by-Step Instructions

#### ✅ 1. Add Score Counter (HTML)

```html
<div id="score">Score: 0</div>
```

- Place it at the **top-right** corner of the game screen.
    

#### ✅ 2. Real-Time Score Logic (JavaScript)

```js
let score = 0;  let scoreInterval = setInterval(() => {   score++;   document.getElementById("score").innerText = "Score: " + score; }, 100);
```

- `setInterval()` runs every 100ms.
- Updates score on the screen in real-time.

#### ✅ 3. Handle Game Over

```js
clearInterval(scoreInterval); // stop score 
alert("Game Over! Your score: " + score); location.reload(); 
// simple restart
```

- You can replace `alert()` with a **custom modal** or "Game Over" screen.
- Add a **Play Again** button if preferred.

#### ✅ 4. Polish Visuals (CSS)

Suggestions:

```css
#score {   
	position: absolute;   
	top: 10px;   
	right: 20px;   
	color: white;   
	font-size: 20px;   
	font-family: sans-serif;   
	background: rgba(0, 0, 0, 0.4);   
	padding: 8px 12px;   
	border-radius: 10px; 
}
```

Other ideas:

- Center the `.game` container.
- Use custom background color or image.
- Add `box-shadow`, rounded corners, clean fonts.
- Use sprite for dino or obstacles.

#### ✅ 5. Restart Game Cleanly

Alternative to `location.reload()`:

```html
<button id="restart" style="display:none;">Play Again</button>
```

```js
document.getElementById("restart").addEventListener("click", () => {   
	window.location.reload(); 
});
```

- Show this button only on game over.

---

### 💡 Pro Tips

|Tip|Details|
|---|---|
|✔ Break into functions|`jump()`, `createObstacle()`, `checkCollision()`, `updateScore()`|
|⏱ Manage intervals|Use `clearInterval()` to stop score or obstacle movement|
|⚠ Avoid alert()|Use modal or overlay for Game Over screen|
|🎨 Personalize|Change sprite, background, or add sound effects|
|🔁 Play Again|Add a button for restarting the game|

---

### 📋 Submission Checklist

✅ Game works with:

- Dino jump using key press
- Obstacle movement with collision
- Score increasing automatically
- Game over on collision
- Option to restart
- Styled layout

✅ Hosted on GitHub Pages / Netlify / Vercel  
✅ GitHub repo link shared  
✅ No external libraries used

---

### 🧪 Example Output

- A basic clone of the Chrome Dino game
- Neatly styled, score tracking in real-time
- Game over message and restart option
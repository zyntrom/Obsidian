Here’s the **Part I: HTML + CSS** code to set up your "Whack-a-Mole" game UI. This gives you a basic working layout with 3 moles, a score display, and a restart button.

---

### ✅ `index.html`

```html
<!DOCTYPE html> 
<html lang="en"> 
	<head>   
		<meta charset="UTF-8">   
		<title>Whack a Mole</title>   
		<link rel="stylesheet" href="style.css"> 
	</head> 
	<body>   
		<div class="container">     
			<h1>Whack a Mole</h1>     
			<div id="score">Score: 0</div>          
			<div class="grid">       
				<div class="mole" id="mole1"></div>       
				<div class="mole" id="mole2"></div>       
				<div class="mole" id="mole3"></div>     
			</div>          
		<button id="restart">Restart</button>   
		</div>    
		<script src="script.js"></script> 
	</body> 
</html>
```

---

### ✅ `style.css`

```css
body {   
	font-family: sans-serif;   
	text-align: center;   
	background-color: #f0f8ff; 
}  
.container {   
	padding: 20px; 
}  h1 {   
	font-size: 2rem;   
	color: #333; 
}  
#score {   
	font-size: 1.5rem;   
	margin: 15px 0; 
}  
.grid {   
	display: flex;   
	justify-content: center;   
	gap: 30px;   
	margin-bottom: 20px; 
}  
.mole {   
	width: 100px;   
	height: 100px;   
	background-color: #ccc;   
	border-radius: 50%;   
	cursor: pointer;   
	transition: background-color 0.2s; }  
.mole.active {   
	background-color: #4caf50; /* Green mole appears */ 
}  
#restart {   
	padding: 10px 20px;   
	font-size: 1rem;   
	cursor: pointer; }

```
---

### 📂 Folder Structure

bash

CopyEdit

`/whack-a-mole/ ├── index.html ├── style.css └── script.js`

---

### ✅ Final Step

Once you’ve created all 3 files (`index.html`, `style.css`, `script.js`) in the same folder, open `index.html` in a browser and you’ll have:

- A clean UI
    
- 3 grey circles (moles)
    
- One mole becomes green every second
    
- Clicking green mole increases score
    
- Restart button resets game
    

Let me know if you want to:

- Add a **timer/level system**
    
- Add **audio/sound effects**
    
- Show **win/lose conditions**
    
- Improve responsiveness or styling
    

Happy whacking! 🎯🐹
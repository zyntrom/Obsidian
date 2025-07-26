## 📒 Whack-a-Mole – Part 1 (HTML + CSS) Notes

### 🎯 Goal

Create the basic visual layout and styling for a simple “Whack-a-Mole” game using only **HTML** and **CSS**, with placeholders for game logic in JavaScript.

---

### 📄 `index.html` Overview

- **Structure**:
    
    - `<!DOCTYPE html>` – HTML5 declaration.
    - `<head>` – includes metadata, title, and links the `style.css` stylesheet.
    - `<body>` contains:
        - `<h1>` – Game title.
        - `<div id="score">` – Displays current score.
        - `<div class="grid">` – Holds 3 mole elements:
            - Each mole is a `<div>` with class `mole` and unique ID (`mole1`, `mole2`, `mole3`).
        - `<button id="restart">` – Restart button.
        - `<script>` tag linking `script.js` for future JavaScript logic.
- **Purpose**: This sets up the full structure and layout for the game board.

---

### 🎨 `style.css` Overview

- **General Styling**:
    - `body` and `.container` center the content and apply basic padding.
    - `h1` and `#score` define text styles.
    - `#restart` styles the restart button.
- **Mole Grid Styling**:
    - `.grid` uses `display: flex` and `gap: 30px` to space moles evenly.
    - `.mole`:
        - Circular shape: `width`, `height`, `border-radius: 50%`.
        - Default grey color (`background-color: #ccc`).
        - `cursor: pointer` and transition effects.
- **Active Mole State**:
    - `.mole.active`: changes color to green (`#4caf50`) to visually show an active (clickable) mole.

Index.html
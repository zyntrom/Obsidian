# 🐢 Logo Turtle Programming (SPE 2025 - Control Structures)

## 🎯 Introduction

Logo Turtle Programming is a fun and visual way to learn programming. You control a turtle (triangle) that moves on the screen and draws by leaving a trail—like a pen on paper.

---

## 🐢 Meet the Turtle

- The turtle follows your commands and draws as it moves.
- Think of it as giving step-by-step dance instructions to a turtle with a marker.

---

## 🧠 Basic Turtle Commands

|**Command**|**What it Does**|**Example / Effect**|
|---|---|---|
|`fd 100` or `fw 100`|Move forward 100 pixels|Straight line ahead|
|`bk 100` or `bw 100`|Move backward 100 pixels|Reverse motion|
|`rt 90`|Turn right by 90° (clockwise)|Clockwise rotation|
|`lt 90`|Turn left by 90° (anti-clockwise)|Counter-clockwise turn|
|`repeat 4 [fd 100 rt 90]`|Repeat a block 4 times|Draws a square|
|`penup` / `pendown`|Lift or place the pen|Move without drawing / draw|
|`color [255 0 0]`|Set RGB color|Example: Red|
|`cs`|Clear screen|Start fresh|

---

## 🧪 Let’s Practice

### 🔲 1. Draw a Square

```
repeat 4 [fd 100 rt 90]
```

- Try modifying:
    - `fd 100` → `fd 200`
    - `rt 90` → `rt 120`
- ✨ **Observation**: Changes shape—angles & lengths matter.

---

### 🟠 2. Draw a Circle

```
arc 1000 180
```

- `1000`: Radius/length of arc
- `180`: Angle in degrees
- This draws a semi-circle or full circle based on angle.

---

### ⭐ 3. Mini Challenge: Draw a Star

Try using:

```
repeat 5 [fd X rt Y]
```

- Play with values of `X` (length) and `Y` (angle)
- Observe how different combinations create stars or polygons


---

## 🤖 Conditional Logic with If-Else

### 🧩 What is If-Else?

A way to **make decisions** in code.

**Syntax (pseudocode):**

```
if condition [     do this ] else [     do that ]
```

**Example in Turtle Logic:**

```
if angle = 90 [     rt 90 ] else [     lt 90 ]
```

- Decision-making allows dynamic control
- Useful for making turtle react to conditions (e.g., user input)

---

## 🖥️ How to Run

- Use the **Logo Interpreter** on your desktop or laptop
- Enter commands in the input box
- Use `clearscreen` or `cs` before each new drawing

---

## 🎨 Learning Outcome

- Build **visual logic** using loops and conditions
- Understand how **angles, lengths, and directions** form different shapes
- Learn basic **control structures** in a fun way
- Visual programming builds strong **problem-solving skills**

---

## 🏁 Summary

|Concept|Key Idea|
|---|---|
|**Movement**|Use `fd`, `bk`, `rt`, `lt` to control turtle|
|**Loops**|`repeat N [commands]` to repeat steps|
|**Color**|`color [R G B]` to set pen color|
|**Drawing**|`pendown` to draw, `penup` to move without|
|**Logic**|`if-else` for decisions|
|**Reset**|`cs` or `clearscreen` to start over|

---

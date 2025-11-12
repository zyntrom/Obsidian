# 🧠 **Kalvium AL 1.30 — Advanced CSS (Animations & Transitions)**

---

## 🎯 **Objective**

Learn how to use **CSS transitions** and **keyframe animations** to add motion, feedback, and interactivity to web interfaces — without JavaScript.

---

## 🏆 **Expected Outcomes**

By the end of this topic, you should be able to:

- Use the `transition` property for smooth changes between states.
- Create and apply multi-step animations using `@keyframes`.
- Control duration, timing, direction, and repetition of animations.
- Trigger motion using pseudo-classes like `:hover`, `:focus`, etc.

---

## 🧩 **1. Introduction to Motion in CSS**

Modern web interfaces rely on **motion** to:

- Provide **visual feedback** (e.g., hover effects).
- Make transitions between states **clear and intuitive**.
- Enhance **user experience** by guiding focus and adding polish.

CSS provides two main systems for motion:

1. **Transitions** → Animate property changes between states.
2. **Keyframe Animations** → Define complex, multi-step animations.

---

## ⚙️ **2. CSS Transitions**

### 📘 Definition

A **transition** animates a change in property values over time — instead of changing instantly.

### 🧱 Syntax

```css
transition: property duration timing-function delay;
```

|Sub-property|Description|Example|
|---|---|---|
|`property`|Which property to animate|`background-color`, `transform`, `all`|
|`duration`|How long the animation lasts|`0.3s`, `500ms`|
|`timing-function`|Speed curve of motion|`ease`, `linear`, `ease-in-out`|
|`delay`|Time to wait before starting|`0.2s`|

---

### 💡 Example: Basic Button Transition

```css
.button {
  background-color: #667eea;
  color: white;
  border-radius: 5px;
  padding: 15px 30px;
  border: none;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.button:hover {
  background-color: #764ba2;
}

```

✅ The background color changes smoothly in **0.3s** when hovered.

---

### 🧩 Transitioning Multiple Properties

```css
.button {
  background-color: #667eea;
  transform: scale(1);
  transition: background-color 0.3s ease, transform 0.2s ease;
}

.button:hover {
  background-color: #764ba2;
  transform: scale(1.05);
}
```

Or animate **all** properties:

```css
transition: all 0.3s ease;
```

---

### ⚖️ Common Timing Functions

|Function|Description|Behavior|
|---|---|---|
|`ease`|Default|Starts slow → fast → slow|
|`linear`|Constant speed|No acceleration|
|`ease-in`|Gradual acceleration|Slow start|
|`ease-out`|Gradual deceleration|Slow end|
|`ease-in-out`|Balanced ease|Smooth start & end|
|`cubic-bezier(x1,y1,x2,y2)`|Custom curve|User-defined motion feel|

---

## 🎞 **3. CSS Animations with `@keyframes`**

### 📘 Definition

**Keyframes** define multiple stages of an animation sequence — like film frames.  
Use them when you need **multi-step** or **continuous** animations (not just hover transitions).

---

### 🧱 Syntax

```css
@keyframes animationName {
  0%   { /* starting state */ }
  50%  { /* middle state */ }
  100% { /* ending state */ }
}
```

Simplified form:

```css
@keyframes fadeIn {
  from { opacity: 0; }
  to   { opacity: 1; }
}
```

---

### 💡 Example: Pulse Animation

```css
@keyframes pulse {
  0%   { transform: scale(1); opacity: 1; }
  50%  { transform: scale(1.05); opacity: 0.8; }
  100% { transform: scale(1); opacity: 1; }
}

.element {
  animation: pulse 2s ease-in-out infinite;
}
```
---

### ⚙️ **Animation Shorthand**

```css
animation: name duration timing-function delay iteration-count direction fill-mode;

```

Example:

```css
animation: pulse 2s ease-in-out 0s infinite alternate both;
```

---

### 🧩 **Animation Sub-properties**

|Property|Purpose|Example|
|---|---|---|
|`animation-name`|Which keyframes to use|`pulse`|
|`animation-duration`|One cycle time|`2s`|
|`animation-timing-function`|Speed curve|`ease-in-out`|
|`animation-delay`|Start delay|`1s`|
|`animation-iteration-count`|Repeats|`infinite`, `3`|
|`animation-direction`|Playback direction|`normal`, `reverse`, `alternate`|
|`animation-fill-mode`|Retain end/start styles|`forwards`, `backwards`, `both`|

---

## ⚡ **4. Combining Transitions & Animations**

You can mix both for responsive, polished effects.

```css
.button {
  background-color: #667eea;
  transition: background-color 0.3s ease, transform 0.2s ease;
  animation: pulse 2s ease-in-out infinite;
}

.button:hover {
  background-color: #764ba2;
  transform: translateY(-3px);
}

@keyframes pulse {
  0%, 100% { box-shadow: 0 0 0 0 rgba(102,126,234,0.7); }
  50% { box-shadow: 0 0 0 10px rgba(102,126,234,0); }
}
```

---

## 🧠 **5. Practical Activity — Animated Button Challenge**

### 🎯 Goal

Add hover transitions + continuous pulse animation.

**Requirements:**

1. **Transition on Hover**
    - Background changes to `#2980b9`
    - Duration: `0.3s`
    - Timing: `ease-in-out`
    - Optional: `transform: scale(1.05)`
2. **Pulse Animation**
    - Animation name: `pulse`
    - Scale: `1 → 1.03 → 1`
    - Duration: `2s`, infinite loop
    - Timing: `ease-in-out`

---

## ⚙️ **6. Animation Best Practices**

|Rule|Description|
|---|---|
|🎯 Keep it meaningful|Use motion for **feedback**, not decoration.|
|⚡ Animate transform/opacity|GPU-accelerated → smooth performance.|
|❌ Avoid layout-triggering properties|Don’t animate `width`, `height`, `top`, or `left`.|
|⏱ Use right durations|UI transitions: `0.2s–0.5s`; Decorative: `1–3s`.|
|♿ Accessibility|Use media query to reduce motion:|

```css
@media (prefers-reduced-motion: reduce) {
  * {
    animation-duration: 0.01ms !important;
    transition-duration: 0.01ms !important;
  }
}
```

---

## 🧩 **7. Additional Example Animations**

### ✅ Fade In

```css
@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}
.element { animation: fadeIn 1s ease-in; }
```

### ➡️ Slide In

```css
@keyframes slideIn {
  from { transform: translateX(-100%); }
  to { transform: translateX(0); }
}
```
### 🔁 Rotate

```css
@keyframes rotate {
  from { transform: rotate(0deg); }
  to { transform: rotate(360deg); }
}
```

### 🏀 Bounce

```css
@keyframes bounce {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-20px); }
}
```

---

## 🧾 **8. Summary**

|Concept|Description|
|---|---|
|**Transitions**|Smoothly change CSS properties between two states.|
|**Animations**|Define multi-step sequences using `@keyframes`.|
|**Shorthand**|`transition:` or `animation:` to combine sub-properties.|
|**Performance Tip**|Animate `opacity` and `transform` only.|
|**Accessibility**|Support `prefers-reduced-motion`.|

---

## 💻 **9. Practice Ideas**

Try applying motion in real components:

- Loading Spinners
- Navigation Hover Effects
- Card Flip Animations
- Progress Bars
- Pulsing Buttons

---

## 📚 **10. References**

- [MDN: Using CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_transitions/Using_CSS_transitions)
- [MDN: Using CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animations/Using_CSS_animations)
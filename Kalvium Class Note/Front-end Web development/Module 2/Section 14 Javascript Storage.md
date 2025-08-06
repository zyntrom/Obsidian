## 🗄️ JavaScript Storage — **Browser Storage**

**Module:** JavaScript Fundamentals  
**Course:** Frontend Web Development | SPE 2025

---

### 🎯 Learning Objectives

- Understand **browser storage** and its uses
- Learn how to use **`localStorage`** for persistent data
- Explore **`sessionStorage`** for temporary data
- Apply storage to real-world use cases like:
    - Games (e.g. high scores)
    - UI preferences (e.g. dark mode)
    - Shopping carts (e.g. temporary items)

---

### 📦 What is Browser Storage?

- Browser storage = a **mini-database in the browser**
- Works **client-side** (no server involved)
- Can remember data **even after closing/reloading** the page (depends on type)

---

### 🔍 Why is Browser Storage Important?

|Benefit|Usefulness|
|---|---|
|**Persistence**|Saves scores, settings, input data|
|**Offline use**|Useful for PWAs, games, local forms|
|**Performance**|Reduces server calls|
|**User experience**|Remembers preferences, themes, etc.|

---

### 🧰 Types of Browser Storage

|Type|Persists after close?|Use Case|
|---|---|---|
|**localStorage**|✅ Yes|High scores, theme, progress|
|**sessionStorage**|❌ No (tab-only)|Temporary form/cart data|

---

### 💾 localStorage — Persistent Data

#### 📌 Stores key-value pairs **across sessions**

**✅ Store Data**

```js
localStorage.setItem('highScore', '1000'); localStorage.setItem('username', 'Kalvian');
```

**📥 Retrieve Data**

```js
const name = localStorage.getItem('username'); 
console.log(name); // Kalvian
```

**🗑️ Remove Data**

```js
localStorage.removeItem('highScore');
```

**♻️ Clear All Storage**

```js
localStorage.clear();
```

---

### ⏳ sessionStorage — Temporary Data

#### 📌 Stores data **only until tab is closed**

**✅ Store Data**

```js
sessionStorage.setItem('theme', 'dark');
```

**📥 Retrieve Data**

```js
const mode = sessionStorage.getItem('theme');
```

**🗑️ Remove Data**

```js
sessionStorage.removeItem('theme');
```

**♻️ Clear All**

```js
sessionStorage.clear();
```

---

### 🆚 localStorage vs sessionStorage

|Feature|`localStorage`|`sessionStorage`|
|---|---|---|
|Persistence|Permanent (until cleared)|Temporary (tab-only)|
|Scope|All tabs/windows|One tab only|
|Use Cases|High scores, theme|Form state, temporary cart|

---

### 🌍 Real-World Examples

#### ✅ localStorage

- Save **high score** in games
- Store **theme preference** (dark/light)
- Save **language** or **font settings**

#### ✅ sessionStorage

- Track **form progress** across steps
- Temporary **shopping cart** before login
- Store **one-time session token**

---

### 🔐 Security Tips

- ⚠️ **Never store passwords** or sensitive info!
- Data is stored in **plain text**.
- Always **validate** and **sanitize** stored values.

---

### 🧪 Try It Now

```js
localStorage.setItem("nickname", "CodeCrust"); alert(localStorage.getItem("nickname")); // Output: CodeCrust
```

✅ Refresh the page — it still remembers!

---

### 📚 Summary

- `localStorage` → **persistent**, survives page reloads
- `sessionStorage` → **temporary**, ends with tab
- Common methods:
    - `setItem(key, value)`
    - `getItem(key)`
    - `removeItem(key)`
    - `clear()`
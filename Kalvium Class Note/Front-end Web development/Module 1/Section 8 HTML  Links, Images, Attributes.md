## ✅ Lesson Overview

You’ve now learned how to make your HTML **interactive and visual** using:

- Hyperlinks (`<a>`)
    
- Images (`<img>`)
    
- Attributes (`id`, `class`, `style`, etc.)
    

This brings life to your previously plain structure.

---

## 🧠 Key Concepts and Syntax

### 🔗 **Hyperlinks** — “The Web’s Teleporters”

html

CopyEdit

`<a href="https://example.com">Click Me!</a>`

- `<a>` = Anchor tag (used to make links)
    
- `href` = "Hypertext REFerence", the **destination URL**
    
- Link text is between opening `<a>` and closing `</a>`
    

#### Open in a New Tab:

html

CopyEdit

`<a href="https://youtube.com" target="_blank">YouTube</a>`

- `target="_blank"` → opens link in a **new browser tab**
    

---

### 🖼️ **Images** — “Visual Appeal in HTML”

html

CopyEdit

`<img src="dog.jpg" alt="Cute dog" width="400" height="300">`

- `<img>` is a **self-closing tag** — no `</img>`
    
- `src` → path/URL of the image
    
- `alt` → description shown if image fails to load (and important for accessibility)
    
- `width` & `height` → control the image size
    

#### Image from the web:

html

CopyEdit

`<img src="https://example.com/cat.png" alt="Cat">`

---

### 🛠️ **Attributes** — “Customize Any HTML Tag”

All HTML elements can have **attributes** — extra data/settings written inside the tag.

#### Example with `<p>`:

html

CopyEdit

`<p id="intro" class="note" style="color: red;" title="This is a tooltip">   This paragraph has styling and a tooltip! </p>`

|Attribute|What it does|
|---|---|
|`id`|Unique identifier (used by CSS/JS)|
|`class`|Grouping for styling with CSS|
|`style`|Inline CSS styling (e.g., `style="color: red;"`)|
|`title`|Shows a tooltip when you hover over the element|

---

## 🧪 Bonus Tip: Combine Everything!

html

CopyEdit

`<h2>My Favorite Website</h2> <p>Click below to visit:</p> <a href="https://kalvium.com" target="_blank">   <img src="kalvium-logo.png" alt="Kalvium Logo" width="200"> </a>`

This makes the **image itself clickable**!

---

## 📌 Key Takeaways

|Concept|Summary|
|---|---|
|Hyperlinks|`<a href="">` lets you link to other web pages|
|Images|`<img src="..." alt="...">` displays pictures|
|Attributes|Add extra information, styling, or behavior to tags|
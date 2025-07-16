## ✅ Summary 

This lesson teaches the **basic structure** of an HTML document and the **core tags** needed to build a webpage. HTML is the **foundation** (or skeleton) of every website — defining structure, content, and layout.

You’ll learn:

- How every HTML document is built (its blueprint)
- What tags like `<html>`, `<head>`, `<body>`, `<h1>`, and `<p>` do
- How to create **well-structured**, readable content

---

## 🧠 Key Notes

### 📐 HTML Document Blueprint (Structure)

```html
<!DOCTYPE html> 
<html lang="en"> 
	<head>   
		<meta charset="UTF-8">  
		<meta name="viewport" content="width=device-width, initial-scale=1.0">   
		<title>My First Webpage</title> 
	</head> 
<body>   <!-- Your visible content goes here --> </body> 
</html>
```

|Tag|Purpose|
|---|---|
|`<!DOCTYPE html>`|Tells browser this is HTML5|
|`<html>`|Root tag of the document|
|`<head>`|Contains meta info (not shown on page)|
|`<body>`|Holds all visible webpage content|

---

### 🧠 `<head>`: Website’s Control Room

This part is **not visible to users**, but **vital for setup**.

```html
<head>   
	<meta charset="UTF-8">   
	<meta name="viewport" content="width=device-width, initial-scale=1.0">   
	<title>My Website</title> 
</head>
```

- `<meta charset="UTF-8">`: Allows special characters and emojis
- `<meta name="viewport"...>`: Makes site responsive on mobile
- `<title>`: Shows in browser tab and search engines

---

### 🖥️ `<body>`: The Stage of Your Website

Everything **inside `<body>`** is shown to users.

```html
<body>   
	<h1>Welcome to My Website</h1>   
	<p>This is a paragraph.</p> 
</body>
```

Includes:

- Text
- Images
- Videos
- Buttons
- Forms
- Links

---

### 📊 Content Hierarchy with Headings

```html
<h1>Main Title</h1> 
<h2>Chapter 1</h2> 
<h3>Section 1.1</h3> 
<h4>Details</h4> 
<h5>Smaller Details</h5> 
<h6>Footnote</h6>
```

- Use **only one `<h1>`** per page (for SEO and accessibility)
- Headings define **structure**, like chapters in a book

---

### 🧾 Organizing Text with Paragraphs

`<p>This is a paragraph of content.</p>`

- Each `<p>` adds **space** between blocks of text
- Makes content **clean, readable, and organized**
- Great for **introductions, descriptions, articles, etc.**

---

### 💬 Comments in HTML

`<!-- This is a comment -->`

- Used to explain code
- Ignored by browser
- Good for documentation

---

## 📘 Core Tags Reference

|Tag|Description|
|---|---|
|`<!DOCTYPE>`|Declares HTML5 document type|
|`<html>`|Root container for the whole document|
|`<head>`|Meta info, title, and page settings|
|`<title>`|Tab title in browser|
|`<meta>`|Character set, viewport settings|
|`<body>`|All visible content goes here|
|`<h1>…<h6>`|Headings — create structure & hierarchy|
|`<p>`|Paragraph — for text blocks|
|`<!-- -->`|Comments — to leave notes in code|

---

## 🧪 Bonus Practice Tip

Try this starter code in VS Code and open in a browser:

```html
<!DOCTYPE html> 
<html lang="en"> 
<head>   
<meta charset="UTF-8">   
<meta name="viewport" content="width=device-width, initial-scale=1.0">   <title>Kalvium Test Page</title> 
</head> 
<body>   
<h1>Hello Kalvians!</h1>   
<h2>This is Module 1</h2>   
<p>We are learning the structure of HTML.</p>   
<p>Paragraphs and headings keep things organized.</p> 
</body> 
</html>
```

---

## 📌 Key Takeaway

> HTML isn’t just about writing code — it’s about building **organized, professional, accessible webpages** from the ground up. Structure matters.
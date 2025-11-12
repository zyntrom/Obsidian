# 📒 6.3 Mini-Project: Library App – Forms & Polish

---

## 🔹 Project Overview

You’ll build a **Library App** that:

1. Displays a **list of books**
2. Allows users to **add new books via a form**
3. Uses **controlled components** for form inputs
4. Clears inputs after submission for a smooth UX

**Key Focus:** Controlled components, state management, dynamic rendering.

---

## 🔹 Learning Objectives

By completing this mini-project, you will learn:

- Capturing **user input** with controlled components
- Updating **React state dynamically**
- Rendering new items based on user input
- Clearing form fields after submission
- Handling forms in React with `useState()`

---

## 🔹 Requirements & Constraints

- Use **React functional components** with `useState()`
- Both form inputs must be **controlled**
- Render books inside a `<ul>` element
- Format: `"Title by Author"`
- Clear inputs after **successful submission**
- Edit **only `App.jsx`**
- Ensure **all tests pass**

---

## 🔹 Controlled Components Refresher

A controlled input:

```js
const [value, setValue] = useState('');

<input
  type="text"
  value={value}
  onChange={(e) => setValue(e.target.value)}
/>

```

- `value` is tied to state
- `onChange` updates the state dynamically

---

## 🔹 Step-by-Step Implementation

### 1️⃣ State Management

```js
const [title, setTitle] = useState('');
const [author, setAuthor] = useState('');
const [books, setBooks] = useState([]);

```

---

### 2️⃣ Form & Input Handlers

```js
const handleSubmit = (e) => {
  e.preventDefault();          // Prevent page reload
  setBooks([...books, { title, author }]); // Add new book
  setTitle('');                // Clear title input
  setAuthor('');               // Clear author input
};

```

---

### 3️⃣ JSX Structure

```js
<form onSubmit={handleSubmit}>
  <input
    type="text"
    value={title}
    onChange={(e) => setTitle(e.target.value)}
    placeholder="Book Title"
  />
  <input
    type="text"
    value={author}
    onChange={(e) => setAuthor(e.target.value)}
    placeholder="Author Name"
  />
  <button type="submit">Add Book</button>
</form>

<ul>
  {books.map((book, index) => (
    <li key={index}>{book.title} by {book.author}</li>
  ))}
</ul>

```

---

### 4️⃣ Key Notes

- **`event.preventDefault()`** is necessary to prevent page reload on form submit
- Always **spread existing books** when adding a new one: `[...books, newBook]`
- Inputs must **reset to empty strings** after adding a book
- **Map over the `books` array** to render the list dynamically

---

## 🔹 Sample Flow

|Action|Result|
|---|---|
|Initial Load|No books displayed|
|Add "The Hobbit" by "Tolkien"|List shows: "The Hobbit by Tolkien"|
|Add "Pride & Prejudice"|List shows:  <br>- The Hobbit by Tolkien  <br>- Pride & Prejudice by Austen|

---

## 🔹 Success Tips

- Keep **state variables separate** for each input
- Bind input `value` to state **every time**
- Use `onChange` to **update state on typing**
- Ensure **unique `key` prop** when rendering list items
- Keep **code clean and readable**

---

## 🔹 Key React Concepts Practiced

- Controlled components (`value` + `onChange`)
- `useState()` for **dynamic forms**
- Event handling in forms (`onSubmit`, `preventDefault`)
- Dynamic rendering with `.map()`
- Resetting form fields after submission
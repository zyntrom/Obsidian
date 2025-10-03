# 🌐 6.4 Client-Side Routing & React Router

---

## 🔹 Concept: Client-Side Routing

- **Problem with old websites:** Each link click reloads the page → slow and clunky
- **Client-side routing:** Navigates between views **without reloading the page**
- Like flipping pages of a book already loaded in memory
- Essential for **Single Page Applications (SPAs)**

**Benefits:**

- Fast, seamless navigation
- Reduces server load
- Works like “instant teleportation” between pages

---

## 🔹 React Router Basics

**React Router** is a library for implementing **client-side routing** in React.

**Install:**

```
npm install react-router-dom
```

**Import Essentials:**

```js
import { BrowserRouter as Router, Route, Switch, Link } from 'react-router-dom';

```

---

## 🔹 Setting Up Routing

### 1️⃣ Wrap your App

```js
function App() {
  return (
    <Router>
      <div>
        <h1>My React App</h1>
      </div>
    </Router>
  );
}

```

- `<Router>` wraps your application to enable routing
- Uses HTML5 history API to sync URL with UI

---

### 2️⃣ Define Components for Pages

```js
function Home() {
  return <h2>Home Page</h2>;
}

function About() {
  return <h2>About Page</h2>;
}

```

---

### 3️⃣ Define Routes with Switch

```js
function Home() {
  return <h2>Home Page</h2>;
}

function About() {
  return <h2>About Page</h2>;
}

```
- `<Route>`: defines a URL → component mapping
- `exact`: ensures **exact path match**
- `<Switch>`: renders **only the first matching route**

---

### 4️⃣ Navigation with Link

```js
<nav>
  <ul>
    <li><Link to="/">Home</Link></li>
    <li><Link to="/about">About</Link></li>
  </ul>
</nav>

```
- `<Link>`: creates navigation without page reload

---

### 5️⃣ Dynamic Routes (Example: Blog Posts)

```js
function Post({ match }) {
  return <h2>Post {match.params.id}</h2>;
}

<Route path="/post/:id" component={Post} />

```

- `:id` is a **route parameter**
- Access via `match.params.id` in the component
- Enables **dynamic URLs** without reload

---

## 🔹 Common Pitfalls

|Issue|Solution|
|---|---|
|Forgetting `<BrowserRouter>`|Wrap entire app with `<Router>`|
|Incorrect route paths|Check leading `/` and case sensitivity|
|Not using `<Switch>`|Only first matched route will render|

---

## 🔹 Summary

- **Client-Side Routing:** Navigate without page reloads
- **React Router:** Enables SPA routing
- **Components:**
    - `<BrowserRouter>` → wrap app
    - `<Route>` → define page routes
    - `<Switch>` → ensures only one route renders
    - `<Link>` → navigation links
- Supports **dynamic route parameters**
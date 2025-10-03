# 🌐 6.7 Assignment | Practice: Basic Routing

---

## 🔹 Objective

By the end of this assignment, you should be able to:

1. Use **React Router** to create multi-page navigation in a SPA
2. Set up routes with `<Routes>` and `<Route>`
3. Navigate between pages using `<Link>`
4. Handle unknown routes with a fallback **NotFound** page

---

## 🔹 Task Breakdown

### 1️⃣ Add Headings in Components

- **Home** → `<h1>Home</h1>`
- **About** → `<h1>About</h1>`
- **Contact** → `<h1>Contact</h1>`
- **NotFound** → `<h1>Not Found</h1>`

---

### 2️⃣ Add Navigation Links

Inside the `<nav>` element, use **Link** from `react-router-dom`:

```js
<nav>
  <ul>
    <li><Link to="/">Home</Link></li>
    <li><Link to="/about">About</Link></li>
    <li><Link to="/contact">Contact</Link></li>
  </ul>
</nav>

```

- Avoid using `<a>` tags; `<Link>` prevents full page reloads

---

### 3️⃣ Set Up Routing

Wrap all routes inside `<Routes>` and define paths:

```js
import { Routes, Route, Link } from 'react-router-dom';
import Home from './Home';
import About from './About';
import Contact from './Contact';
import NotFound from './NotFound';

function App() {
  return (
    <div>
      <nav>
        <ul>
          <li><Link to="/">Home</Link></li>
          <li><Link to="/about">About</Link></li>
          <li><Link to="/contact">Contact</Link></li>
        </ul>
      </nav>
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/about" element={<About />} />
        <Route path="/contact" element={<Contact />} />
        <Route path="*" element={<NotFound />} /> {/* Wildcard route */}
      </Routes>
    </div>
  );
}

export default App;

```

---

### 4️⃣ Notes & Tips

|Step|Tip|
|---|---|
|Navigation|Use `<Link>` instead of `<a>`|
|Route Definition|Wrap all routes in `<Routes>`|
|Wildcard Route|Use `"*"` path for undefined URLs|
|Test Cases|Exact headings matter for passing tests|

---

✅ **Key Takeaways**

- React Router lets you build **multi-page experiences in SPAs**
- `<Routes>` + `<Route>` define which component renders for each URL
- `<Link>` allows **client-side navigation** without page reloads
- `"*"` path handles all **unknown routes gracefully**
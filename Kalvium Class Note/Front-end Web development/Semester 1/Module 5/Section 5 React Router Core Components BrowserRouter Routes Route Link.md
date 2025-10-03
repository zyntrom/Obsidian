# 🌐 6.5 React Router: Core Components

---

## 🔹 React Router Overview

- Library to **navigate between views without page reloads**
- Essential for **Single Page Applications (SPAs)**
- Enables smooth transitions like “magic portals” between pages

---

## 🔹 BrowserRouter

- Wraps your entire app to **enable routing**
- Uses **HTML5 history API** to sync URL with UI
- Acts like the **foundation of a house** for routing

**Usage:**

```js
import { BrowserRouter } from 'react-router-dom';

function App() {
  return (
    <BrowserRouter>
      {/* App content */}
    </BrowserRouter>
  );
}

```

---

## 🔹 Routes & Route

### Routes

- Container for all `<Route>` components
- Ensures **only one route renders at a time**
- Think of it as a **traffic controller**

### Route

- Maps a **URL path → component**
- Renders the component when URL matches path

**Usage:**

```js
import { Routes, Route } from 'react-router-dom';
import Home from './Home';
import About from './About';

function App() {
  return (
    <Routes>
      <Route path="/" element={<Home />} />
      <Route path="/about" element={<About />} />
    </Routes>
  );
}

```

- `path`: URL path to match
- `element`: Component to render when path matches

---

## 🔹 Link

- Creates **hyperlinks for navigation**
- Updates URL without reloading page
- Like a **doorway connecting rooms** in your app

**Usage:**

```js
import { Link } from 'react-router-dom';

function Navbar() {
  return (
    <nav>
      <ul>
        <li><Link to="/">Home</Link></li>
        <li><Link to="/about">About</Link></li>
      </ul>
    </nav>
  );
}

```

- Clicking a `<Link>` updates the URL and renders the corresponding component

---

## 🔹 Putting It Together

```js
import { BrowserRouter, Routes, Route, Link } from 'react-router-dom';
import Home from './Home';
import About from './About';
import Contact from './Contact';

function App() {
  return (
    <BrowserRouter>
      <nav>
        <Link to="/">Home</Link>
        <Link to="/about">About</Link>
        <Link to="/contact">Contact</Link>
      </nav>
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/about" element={<About />} />
        <Route path="/contact" element={<Contact />} />
      </Routes>
    </BrowserRouter>
  );
}

```

✅ **What happens:**

- `<BrowserRouter>` enables routing
- `<Routes>` controls which `<Route>` renders
- `<Route>` maps path → component
- `<Link>` lets users navigate without reloads

---

## 🔹 Benefits

|Component|Purpose / Advantage|
|---|---|
|**BrowserRouter**|Enables SPA routing; clean URLs; uses HTML5 history API|
|**Routes / Route**|Maps URL → component; allows dynamic routing|
|**Link**|Smooth navigation; SEO-friendly; avoids page reloads|

---

## 🔹 Key Notes

- Always **wrap app with BrowserRouter**
- Use **Routes** instead of Switch (React Router v6)
- Use **element prop** instead of component prop
- Links prevent full page reloads → better UX
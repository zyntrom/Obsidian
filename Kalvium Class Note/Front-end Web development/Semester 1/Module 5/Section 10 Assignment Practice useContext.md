# 🌐 6.10 Assignment | Practice: useContext

---

## 🔹 Objective

By the end of this lesson, you will be able to:

1. Use `createContext` and `useContext` to **share state across multiple components**.
2. Manage a **global theme state** using a custom context provider.
3. Update the UI based on **context values from any component**.

---

## 🔹 Task Overview

You are building a **Theme Toggle feature** in React using Context.

### Steps:

---

### 1️⃣ Create a Theme Context

```

```

- `createContext()` returns a context object with `Provider` and `Consumer`.
- Default value can be `null` or `"light"`.

---

### 2️⃣ Build a ThemeProvider Component

`import React, { useState } from 'react'; import { ThemeContext } from './ThemeContext';  export function ThemeProvider({ children }) {   const [theme, setTheme] = useState('light');    const toggleTheme = () => {     setTheme(theme === 'light' ? 'dark' : 'light');   };    return (     <ThemeContext.Provider value={{ theme, toggleTheme }}>       {children}     </ThemeContext.Provider>   ); }`

- Wrap all components needing the **theme** with `ThemeProvider`.
    
- `toggleTheme` switches between `"light"` and `"dark"`.
    
- `value={{ theme, toggleTheme }}` shares both state and function.
    

---

### 3️⃣ Update Header Component

`import React, { useContext } from 'react'; import { ThemeContext } from './ThemeContext';  function Header() {   const { theme } = useContext(ThemeContext);    return <h1>Current Theme: {theme}</h1>; }`

- `useContext(ThemeContext)` allows **direct access to the theme**.
    

---

### 4️⃣ Update ThemeToggleButton Component

`import React, { useContext } from 'react'; import { ThemeContext } from './ThemeContext';  function ThemeToggleButton() {   const { toggleTheme } = useContext(ThemeContext);    return <button onClick={toggleTheme}>Toggle Theme</button>; }`

- Button calls `toggleTheme` from context to **update theme globally**.
    

---

### 5️⃣ Wrap App with ThemeProvider

`import React from 'react'; import { ThemeProvider } from './ThemeProvider'; import Header from './Header'; import ThemeToggleButton from './ThemeToggleButton';  function App() {   return (     <ThemeProvider>       <Header />       <ThemeToggleButton />     </ThemeProvider>   ); }  export default App;`

- Ensures **Header** and **ThemeToggleButton** can access the shared theme state.
    

---

## 🔹 Key Notes

- Use `React.createContext()` to create a context object.
    
- Use `useContext(ThemeContext)` in any child component.
    
- `ThemeProvider` wraps the app component tree to provide global state.
    
- `toggleTheme` updates state for **all components** consuming the context.
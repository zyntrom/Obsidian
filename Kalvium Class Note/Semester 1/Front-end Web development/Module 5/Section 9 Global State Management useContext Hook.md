# 🌐 6.9 Global State Management: useContext Hook

---

## 🔹 What is the `useContext` Hook?

- `useContext` is a **React built-in hook** that allows sharing state across components **without prop drilling**.
- Think of it as a **school announcement system** instead of whispering messages down a chain.

**Analogy:**

- **Context** = menu board
- **Provider** = barista updating menu
- **useContext** = customer reading menu
- Everyone gets the info without intermediaries.

---

## 🔹 Why `useContext` is Important

1. Eliminates prop drilling → simpler state management.
2. Improves code readability → less boilerplate.
3. Increases component reusability → decouples from parent-child chains.
4. Ideal for shared data: theme, authentication, language, user info, etc.

---

## 🔹 How to Use `useContext` Hook

**Three steps:**

### 1️⃣ Create a Context

```js
import React from 'react';
const MyContext = React.createContext(null); // default value

```

---

### 2️⃣ Provide a Context Value

Wrap components needing access with `<Context.Provider>`:

```js
function App() {
  const [theme, setTheme] = React.useState('light');

  return (
    <MyContext.Provider value={{ theme, setTheme }}>
      <Header />
      <Main />
    </MyContext.Provider>
  );
}

```

- `value` prop can be **any JS value**: object, array, function, etc.

---

### 3️⃣ Consume the Context Value

Use `useContext` in functional components:

```js
import React, { useContext } from 'react';

function Header() {
  const { theme, setTheme } = useContext(MyContext);

  return (
    <header>
      Theme: {theme}
      <button onClick={() => setTheme(theme === 'light' ? 'dark' : 'light')}>
        Toggle Theme
      </button>
    </header>
  );
}

```

- Components can **read and update context** without props.

---

## 🔹 Common Use Cases

### 1️⃣ Theme Management

```js
const ThemeContext = createContext({ 
	theme: 'light', 
	toggleTheme: () => {} 
});

```

- Apply consistent colors/fonts across multiple components.

---

### 2️⃣ User Authentication

```js
const AuthContext = createContext({ 
	isAuthenticated: false, 
	user: null, 
	login: () => {}, 
	logout: () => {} 
});
```

- Share auth status and user info globally.

---

### 3️⃣ Language Settings

```js
const LanguageContext = createContext({ 
	currentLanguage: 'en', 
	setLanguage: () => {}, 
	translations: {} 
});
```

- Share multilingual content dynamically across components.

---

## 🔹 Task Example

**Scenario:** Blog app with `Header`, `PostList`, and `Footer`.

- `Header` shows current user name.
- `PostList` fetches posts based on user preferences.

**Solution:**

1. Create a `UserContext` with user info and preferences.
2. Wrap `Header` and `PostList` with `UserContext.Provider`.
3. Consume `useContext(UserContext)` in each component.

- **No prop drilling needed.**

---

## 🔹 Key Takeaways

1. `useContext` = share state globally without prop drilling.
2. Steps: **create context → provide value → consume with useContext**.
3. Useful for:
    - Theme management
    - User authentication
    - Language/locale settings
4. Improves readability, maintainability, and reusability.
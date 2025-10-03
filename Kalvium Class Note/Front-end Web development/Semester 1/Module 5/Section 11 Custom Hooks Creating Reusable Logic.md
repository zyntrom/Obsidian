# 🛠 6.11 Custom Hooks | Creating Reusable Logic

---

## 🔹 Objective

By the end of this lesson, you will be able to:

1. Understand what **custom hooks** are and why they’re useful.
2. Create a **custom hook** in React.
3. Reuse **stateful logic** between components without copy-pasting.
4. Identify use cases where **custom hooks simplify component logic**.

---

## 🔹 What is a Custom Hook?

- A **custom hook** is a JavaScript function that:
    - Starts with `use`
    - Calls other React hooks (`useState`, `useEffect`, `useContext`, etc.)
- Purpose: **Extract and reuse logic** without repeating code.
- Important: Custom hooks **don’t render UI**, they only handle logic.

**Analogy:**

- Custom hook = Pre-made sauce
- Component = Dish
- React hooks inside custom hook = Fresh ingredients

---

## 🔹 Why Use Custom Hooks?

- Promote **code reusability**
- Improve **readability**
- Simplify **testing**
- Follow the **DRY principle**

---

## 🔹 How to Create a Custom Hook

1️⃣ **Define a function starting with `use`**

```js
import { useState, useEffect } from 'react';

function useFetchData(url) {
  // logic here
}

```

2️⃣ **Use React hooks inside the function**

```js
function useFetchData(url) {
  const [data, setData] = useState(null);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState(null);

  useEffect(() => {
    async function fetchData() {
      try {
        const response = await fetch(url);
        const json = await response.json();
        setData(json);
      } catch (error) {
        setError(error);
      } finally {
        setLoading(false);
      }
    }
    fetchData();
  }, [url]);

  return { data, loading, error };
}

```

3️⃣ **Return values or functions**

- Components using this hook will access the returned values:

```js
function MyComponent() {
  const { data, loading, error } = useFetchData('https://api.example.com/data');

  if (loading) return <p>Loading...</p>;
  if (error) return <p>Error: {error.message}</p>;

  return <ul>{data.map(item => <li key={item.id}>{item.name}</li>)}</ul>;
}

```

---

## 🔹 Use Cases for Custom Hooks

1️⃣ **Form Management**

`function useForm(initialValues, validateSubmit) {   const [values, setValues] = useState(initialValues);   const [errors, setErrors] = useState({});   const [isSubmitting, setIsSubmitting] = useState(false);    const handleChange = event => {     setValues({ ...values, [event.target.name]: event.target.value });   };    const handleSubmit = event => {     event.preventDefault();     setErrors(validateSubmit(values));     setIsSubmitting(true);   };    return { handleChange, handleSubmit, values, errors, isSubmitting }; }`

2️⃣ **Local Storage Management**

`function useLocalStorage(key, initialValue) {   const [storedValue, setStoredValue] = useState(() => {     try {       const item = window.localStorage.getItem(key);       return item ? JSON.parse(item) : initialValue;     } catch {       return initialValue;     }   });    useEffect(() => {     window.localStorage.setItem(key, JSON.stringify(storedValue));   }, [key, storedValue]);    return [storedValue, setStoredValue]; }`

3️⃣ **Window Size Tracking**

`function useWindowSize() {   const [windowSize, setWindowSize] = useState({ width: window.innerWidth, height: window.innerHeight });    useEffect(() => {     function handleResize() {       setWindowSize({ width: window.innerWidth, height: window.innerHeight });     }     window.addEventListener('resize', handleResize);     return () => window.removeEventListener('resize', handleResize);   }, []);    return windowSize; }`

---

## 🔹 Task Idea

- Imagine building an **e-commerce app**:
    
    - `Cart` component shows the number of items.
        
    - `Checkout` component calculates the total price.
        
- Create a **useCart hook** to **share cart logic** across multiple components without prop drilling.
    

**Discussion:** Compare using a **custom hook** vs **Redux** or **Context** for state management.

---

## 🔹 Key Takeaways

- Custom hooks are **functions starting with `use`** that call other hooks.
    
- They **extract reusable logic** from components.
    
- Common uses:
    
    - Form state management
        
    - API data fetching
        
    - Local storage access
        
    - Window size tracking
        
- Benefits: **cleaner, reusable, testable code**
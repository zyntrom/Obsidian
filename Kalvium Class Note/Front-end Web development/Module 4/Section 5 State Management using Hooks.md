# React State Management using Hooks

## Story of Hooks

- **Before Hooks**: State management was possible only in **class components**. They were powerful but clunky (like **manual gears** in a car).
- **With Hooks**: Functional components got built-in tools to handle state and side effects (like **automatic gears**) → cleaner, faster, reusable logic.

---

## Key Hooks and Their Analogies

|Hook|Primary Use|Analogy|
|---|---|---|
|**useState**|Manages local component state|Sticky notes → quick, personal notes|
|**useEffect**|Handles side effects (after events)|Reminder app → alerts after events|
|**useContext**|Shares global state across components|Wi-Fi router → connect once, access everywhere|
|**useReducer**|Handles complex state logic|Traffic controller → organizes many changes|
|**useRef**|References values/DOM elements|Bookmark → remembers position/value|
|**useMemo**|Optimizes expensive calculations|Speed dial → saves time by reusing results|
|**useCallback**|Optimizes function references|Prepped ingredients → ready for reuse|

👉 In this lesson, focus is on **useState, useEffect, useContext**.  
👉 Advanced (Part 2) will cover **useReducer, useMemo, useCallback**.

---

## useState: Local State Management

- **Definition**: Manages state inside a single component.
- **Analogy**: Magic whiteboard — you can write, erase, and rewrite data anytime.
- **Usage**: Perfect for **simple values** like form inputs, toggles, counters.

**Example: Counter App**

- Increment count.
- Add **Decrement** button.
- Add **Reset** button (set count back to 0).

---

## useEffect: For Side Effects

- **Definition**: Lets you run code in response to state/lifecycle changes.
- **Side effects** = actions outside the component’s render (e.g., API calls, timers, subscriptions).
- **Analogy**: Reminder app — triggers alerts after specific events.

**Example: Fetching Data on Load**

- Fetch post when component loads.
- Add button → fetch a **different post** using `useState`.
- Add input field → fetch based on **post ID entered by user**.

---

## useContext: Managing Global State

- **Definition**: Shares state across multiple components without **prop drilling**.
- **Analogy**: Wi-Fi router → connect once, access anywhere.
- **Usage**: Best for **themes, authentication, user preferences**, etc.

**Example: Theme Switcher**

- Switch between **light/dark theme**.
- Save theme in `localStorage` → persist after refresh.
- Add **Reset button** → reset theme to "light".

---

## Why State Management Hooks Matter

- **useState** → for **isolated local state**.
- **useContext** → for **shared global state**.
- **useReducer** (coming soon) → for **complex, predictable state transitions**.

⚡ Together, these can **replace Redux** in small to medium apps.

---

## Rules of Hooks (Important!)

1. Only call Hooks at the **top level** of your component (not inside loops, conditions, or nested functions).
2. Only call Hooks from **React functions** (functional components or custom hooks).

---

## Post-Class Reading

- 🔗 `useState()` Hook in React
- 🔗 Complete Guide to `useEffect`
- 🔗 `useContext` Reference Guide

---

## Next Up (Part 2 – Advanced State Management)

- **useReducer** → manage multiple state variables & actions
- **useMemo** → cache derived values for performance
- **useCallback** → prevent unnecessary re-renders with memoized functions

---
```embed
title: "10 React Hooks Explained // Plus Build your own from Scratch"
image: "https://i.ytimg.com/vi/TNhaISOUy6Q/maxresdefault.jpg"
description: "React hooks provide a highly-efficient was to tap into framework features and organize reactive logic. Learn how use every built-in React hook https://firesh..."
url: "https://youtu.be/TNhaISOUy6Q"
favicon: ""
aspectRatio: "56.25"
```

```embed
title: "Rules of Hooks In React | React Hooks"
image: "https://i.ytimg.com/vi/jzrY8fG7HoI/maxresdefault.jpg"
description: "Please like, share and subscribe if you find the video useful. Checkout the Playlists: 👉 FrontEnd JavaScript Interview Questions: https://www.youtube.com/wa..."
url: "https://youtu.be/jzrY8fG7HoI"
favicon: ""
aspectRatio: "56.25"
```

## Summary

- **React Hooks** = new foundation for state in modern React.
- **useState** → Local state (counters, inputs, toggles).
- **useEffect** → Side effects (API calls, timers, reactions to state).
- **useContext** → Global state sharing (themes, auth, settings).
- Hooks make functional components **stateful, reusable, and optimized**.
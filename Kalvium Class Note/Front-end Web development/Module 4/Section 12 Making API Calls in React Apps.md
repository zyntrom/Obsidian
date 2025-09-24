# 📌 Quick Revision Notes – Making API Calls in React Apps

## 🎯 Learning Objectives

- Integrate API calls in React applications.
- Use `useEffect` for managing side effects.
- Apply best practices for fetching & handling data.
- Explore different API integration approaches.

---

## 🔑 Strategies for API Calls

- Use `useEffect` → run API calls on component mount or dependency change.
- Use `async/await` → cleaner & more readable code.
- Add **error handling** → user-friendly error messages.

---

## ⚡ Using `useEffect` for API Calls

- `useEffect` handles **side effects** (data fetch, subscriptions, DOM updates).
- API calls usually happen on **mount** or when **dependencies change**.

**Key Flow:**

1. `useState` → store **data**, **loading**, and **error**.
2. `useEffect` → run API call.
3. `fetchData (async)` → perform API request.
4. `try / catch / finally` → handle success, errors, and cleanup.
5. Conditional rendering → show **loading**, **error**, or **data**.

---

## ✅ Best Practices

- **Centralize API calls** → utility module.
- Use **environment variables** for API keys & endpoints.
- Show **loading indicators** during fetch.
- Provide **clear error messages** on failure.
- Optimize → memoization, lazy loading.

---

## ⚙️ Approaches to API Integration

- **Fetch API** → built-in, simple.
- **Axios** → feature-rich, auto JSON parsing, better error handling.
- **React Query** → caching, syncing, server state management.
- **SWR** → lightweight, caching, revalidation.

👉 Pick based on project needs: simplicity vs caching vs advanced features.

---

## 🔐 Managing API Keys & Endpoints

- **Environment Variables** (e.g., `.env` with `REACT_APP_API_KEY`).
- **Config Files** for different environments (dev, prod).
- **Secure Storage** (Vault, AWS Secrets Manager) for sensitive keys.

---

## ⚠️ Error Handling & Loading States

- **Loading State** → show spinner/message while fetching.
- **Error State** → catch errors & show meaningful messages.

---

## 📚 Additional Resources

- React Official Docs
- Axios Docs

---

## 📝 Summary

- Use `useEffect` to manage API call side effects.
- Centralize API calls → reusability & maintainability.
- Store API keys in **environment variables**.
- Always handle **loading** & **error states** for good UX.
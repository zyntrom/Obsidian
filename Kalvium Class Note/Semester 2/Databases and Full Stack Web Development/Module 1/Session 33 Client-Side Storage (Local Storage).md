# 🧠 Kalvium AL — 1.33 Client-Side Storage (Local Storage)

---

## 🎯 Objective

Learn how to persist client-side data across page refreshes using the browser **localStorage** API. Build a small Notes app (React + Vite) that saves, loads, and deletes notes from localStorage.

---

## 🔎 Why this matters

`useState` keeps UI data in memory only — refresh the page and it’s gone. `localStorage` lets you store small amounts of JSON-serializable data **persistently** in the user's browser (survives refreshes, tabs, and closing the browser).

---

## ⚙️ Key Concepts

- **localStorage stores strings only.** Convert objects/arrays with `JSON.stringify()` before saving and `JSON.parse()` after reading.
- `localStorage.getItem(key)` → returns string or `null` if missing.
- Use a consistent key (e.g. `'userNotes'`).
- `sessionStorage` exists too, but data there survives only the current session.
- Keep localStorage usage simple and defensive (handle `null` and invalid JSON).

---

## ✅ App requirements (Notes App)

- Single `NotesApp` component (React).
- Add notes (prevent empty notes).
- Delete individual notes.
- Persist notes to localStorage so they survive refresh.
- Load notes from localStorage on mount.
- Show empty-state when no notes.
- Basic CSS for presentation.
- Use `useEffect` and `useState`.

---

## 🧭 Implementation plan (phases)

1. Initialize Vite + React project:
    
```bash
npm create vite@latest notes-app --template react 
cd notes-app 
npm install 
npm run dev
```
    
2. Create `NotesApp.jsx` with state:
    - `const [notes, setNotes] = useState([]);`
    - `const [inputValue, setInputValue] = useState('');`
3. Load notes on mount:
    - `useEffect(() => { /* read from localStorage */ }, []);`
4. Save notes whenever they change:
    - `useEffect(() => { /* write to localStorage */ }, [notes]);`
5. Implement `addNote()`:
    - Trim input, block empty strings, append to `notes`, clear input.
6. Implement `deleteNote(index)`:
    - Filter notes by index and update state.
7. Add UI & basic styles, test add/delete, then test persistence.

---

## 🧩 Example component (complete, minimal)

```js
// src/NotesApp.jsx
import { useState, useEffect } from 'react';
import './App.css';

export default function NotesApp() {
  const STORAGE_KEY = 'userNotes';
  const [notes, setNotes] = useState([]);
  const [inputValue, setInputValue] = useState('');

  // Load notes once on mount
  useEffect(() => {
    const saved = localStorage.getItem(STORAGE_KEY);
    if (saved) {
      try {
        const parsed = JSON.parse(saved);
        if (Array.isArray(parsed)) setNotes(parsed);
      } catch (err) {
        console.error('Failed to parse notes from localStorage', err);
        setNotes([]);
      }
    }
  }, []);

  // Save whenever notes change
  useEffect(() => {
    try {
      localStorage.setItem(STORAGE_KEY, JSON.stringify(notes));
    } catch (err) {
      console.error('Failed to save notes to localStorage', err);
    }
  }, [notes]);

  const addNote = () => {
    const trimmed = inputValue.trim();
    if (trimmed === '') return alert('Please enter a note');
    setNotes(prev => [...prev, trimmed]);
    setInputValue('');
  };

  const deleteNote = (index) => {
    setNotes(prev => prev.filter((_, i) => i !== index));
  };

  return (
    <div className="notes-app">
      <h1>📝 My Personal Notes</h1>

      <div className="input-row">
        <input
          type="text"
          placeholder="Write your note here..."
          value={inputValue}
          onChange={(e) => setInputValue(e.target.value)}
          onKeyDown={(e) => { if (e.key === 'Enter') addNote(); }}
        />
        <button onClick={addNote}>Add Note</button>
      </div>

      <section className="notes-list">
        <h2>Your Notes:</h2>
        {notes.length === 0 ? (
          <p className="empty">No notes yet. Add your first note above!</p>
        ) : (
          <ul>
            {notes.map((note, idx) => (
              <li key={idx}>
                <span>{note}</span>
                <button className="delete" onClick={() => deleteNote(idx)}>Delete</button>
              </li>
            ))}
          </ul>
        )}
      </section>

      <p className="hint">✓ All notes are automatically saved!</p>
    </div>
  );
}
```

---

## 💡 Important implementation details & tips

- **Guard parsing**: always wrap `JSON.parse` in `try/catch`.
- **Use arrays** for notes and sensible indexes/IDs. For production consider using stable IDs instead of array index keys.
- **Avoid infinite loops**: when saving to localStorage in `useEffect`, depend **only** on `notes`.
- **Prevent blank notes**: `trim()` the input and reject empty string.
- **Check DevTools** → Application → Local Storage to inspect `'userNotes'`.
- If localStorage is full or throws, catch errors and notify (console or UI).

---

## 🧪 Manual test checklist

-  Start app, see no notes message.
-  Add a note; it appears in the list.
-  Press Enter to add (optional).
-  Delete a note; it disappears.
-  Refresh page; previously saved notes still present.
-  localStorage contains `'userNotes'` stringified JSON array.
-  No console errors during load/save.

---

## ⚠️ Common gotchas

- Forgetting `JSON.stringify` when saving — localStorage will store `[object Object]` for objects.
- Trying to `JSON.parse(null)` — check `getItem` result first.
- Using index as a key while allowing reordering — indices can cause UI bugs; OK if only append/delete.
- Two-way updates between state and storage without proper dependencies — leads to loops.

---

## 🧾 Summary

- `localStorage` is ideal for small, persistent client-side data (preferences, notes, theme).
- Combine `useState` (runtime state) + `useEffect` (load/save side effects) for persistence.
- Always stringify on save and parse on load safely.
- Keep UX simple: prevent empty entries, show empty-state, and confirm notes auto-save.
# Setting up a React Project with Vite

## Why Vite?

- Old React setups were **slow & complex**.
- **Vite** = modern tool for faster & simpler setup.

### Benefits of Vite:

- ⚡ **Fast development startup**
- 🔧 **Minimal configuration**
- 🛠️ **Modern features** (ESM, hot reload)
- Lets you **focus on coding** instead of setup.

---

## Steps to Create a React App with Vite

1. **Create a new project**
    `npm create vite@latest my-react-app --template react`
    - `npm create vite@latest` → Runs Vite’s project creation tool.
    - `my-react-app` → Name of project folder (can be any name).
    - `--template react` → Sets up React template.
2. **Navigate into project folder**
    `cd my-react-app`
    - `cd` = change directory → moves into your project folder.
3. **Install dependencies**
    `npm install`
    - Downloads and installs all required packages for React + Vite.
4. **Start development server**
    `npm run dev`
    - Runs Vite server.
    - Opens app in browser at **[http://localhost:5173/](http://localhost:5173/)**.
    - Auto-reloads when you make code changes.

---

## Project Structure

```
my-react-app/
├── node_modules/       → Installed dependencies
├── public/             → Static assets (e.g., vite.svg)
├── src/                → React code & styles
│   ├── App.css         → Styles for App component
│   ├── App.jsx         → Main UI component
│   ├── assets/         → Images/assets (e.g., react.svg)
│   ├── index.css       → Global styles
│   └── main.jsx        → Entry point (connects React to browser)
├── .gitignore          → Files to ignore in git
├── index.html          → Root HTML file (React renders here)
├── package-lock.json   → Dependency lock file
├── package.json        → Project info & dependencies
└── vite.config.js      → Vite configuration

```

---

## Key Files

- **main.jsx** → Entry point, renders `<App />` into the browser.
- **App.jsx** → Main UI component (what you first see).
- **index.html** → Root HTML file where React mounts.
- **index.css** → Global CSS.
- **package.json** → Manages dependencies & project info.

---

## Try It Out

1. Start server:
    `npm run dev`
2. Visit: **[http://localhost:5173/](http://localhost:5173/)**
3. Edit `App.jsx` → Save → Browser auto-updates with changes.

---

## Summary

- **Vite** = fastest way to set up a React project.
- Command to create app:
    `npm create vite@latest my-react-app --template react`
- Steps: install → run server → edit code.
- **main.jsx** = entry point, **App.jsx** = main UI component.
- Runs on **[http://localhost:5173/](http://localhost:5173/)** with hot reload.
## Module 1 Project Integration — _Blogify Foundation_

### 🎯 Objective

Integrate all skills learned in Module 1 to create a **functional, version-controlled backend foundation** for the “Blogify” project.

You should now be able to:

- Create a Node.js server
- Manage a project with NPM
- Organize scalable folders
- Use Git + GitHub professionally

---

## 🔧 Integration Checklist (Blueprint)

### 1️⃣ Professional Folder Structure

Organize your project for clarity and scalability.

```bash
/blogify-api
├── .git/
├── .gitignore
├── README.md
├── package.json
├── package-lock.json
└── src/
    ├── controllers/
    ├── routes/
    ├── services/
    ├── utils/
    └── index.js

```

**Notes**

- Top level: config and metadata files (`package.json`, `.gitignore`, etc.)
- `src/`: contains all application logic.
- Subfolders can remain empty for now; only structure matters.

---

### 2️⃣ NPM Configuration (`package.json`)

**Purpose:** Holds project metadata, dependencies, and automation scripts.

**Requirements**

- Created using
    
    `npm init -y`
    
- `nodemon` installed as a **devDependency**
    
    `npm install nodemon -D`
    

**Scripts Section Example**

`"scripts": {   "start": "node src/index.js",   "dev": "nodemon src/index.js" }`

- `start` → runs production server using `node`.
    
- `dev` → runs development server with automatic restart via `nodemon`.
    

---

### 3️⃣ Main Entry Point — `src/index.js`

**Purpose:** Launches a basic web server to verify project runs correctly.

**Implementation Requirements**

- Use Node’s core **`http`** module.
    
- File must be inside `src/`.
    
- Respond with message:
    
    `Blogify API is running!`
    
- Default port: **3000**
    

**Example**

`const http = require("http");  const server = http.createServer((req, res) => {   res.writeHead(200, { "Content-Type": "text/plain" });   res.end("Blogify API is running!"); });  server.listen(3000, () => {   console.log("Server running on port 3000"); });`

---

### 4️⃣ Version Control Setup

**Files to Include**

- `.gitignore` → must ignore `node_modules/`
    
    `node_modules`
    
- `README.md` → basic description of the project.  
    Example content:
    
    `# Blogify API Backend foundation for the Blogify project.`
    

**Purpose:** Keeps repository clean and professional for collaboration.

---

## ⚙️ Professional Setup Workflow

### Step 1: Create Remote Repository

1. On GitHub → create a new **public repo** named `blogify-api`.
    
2. Initialize it with:
    
    - `README.md`
        
    - `.gitignore` (select **Node** template)
        

---

### Step 2: Set Up Locally

`# Clone the repo git clone https://github.com/<YourUsername>/blogify-api.git cd blogify-api code .`

---

### Step 3: Work on a Feature Branch

Never code on `main`.

`git checkout -b feat/setup-initial-structure`

---

### Step 4: Build Project Foundation

1. **Initialize npm**
    
    `npm init -y`
    
2. **Install nodemon**
    
    `npm install nodemon -D`
    
3. **Edit `package.json`** → add `start` and `dev` scripts.
    
4. **Create Folder Structure** → `src/` with subfolders.
    
5. **Create Server** → add `src/index.js` with “Blogify API is running!”.
    
6. **Test server**
    
    `npm run dev`
    
    → should print “Server running on port 3000”.  
    Stop with `Ctrl + C`.
    

---

### Step 5: Commit, Push, and Open Pull Request

`git add . git commit -m "feat: set up initial project structure and http server" git push origin feat/setup-initial-structure`

Then:

1. On GitHub, click **“Compare & pull request”**.
    
2. Open a PR to merge your feature branch into `main`.
    
3. Verify all new files/folders appear in the _Files changed_ tab.
    

---

## 🧩 Assignment — Showcase Your Foundational Architecture

**You must submit:**

1. **Pull Request Link**
    
    - Copy the PR URL from GitHub.
        
2. **Video Explanation (1–2 min)**
    
    - Show your open PR and explain your branch workflow.
        
    - Show VS Code folder structure (`src`, `routes`, `controllers`, etc.).
        
    - Run `npm run dev` and display output.
        
    - Show `http://localhost:3000` in browser.
        
    - Upload video to Google Drive (anyone with link = view).
        
    - Submit PR + Video links.
        

---

## 🧭 Summary

|Component|Purpose|Key Command / File|
|---|---|---|
|**Folder Structure**|Organize code modules|`/src` with subfolders|
|**package.json**|Project metadata + scripts|`npm init -y`|
|**nodemon**|Auto-restart dev server|`npm install nodemon -D`|
|**Server File**|Main entry point|`src/index.js`|
|**.gitignore**|Ignore node_modules|add `node_modules`|
|**Branch & PR**|Professional workflow|`git checkout -b` + PR|
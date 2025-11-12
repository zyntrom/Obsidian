# ✅ **1. Purpose of This Chapter**

This section explains:

- What you need to install to start backend development with Node.js
- What Node.js actually includes
- The roles of **Node.js** and **NPM**
- How to install and verify them on different operating systems

---

# ✅ **2. What You Install When You Install Node.js**

When you install Node.js, you actually get two major tools:

### **A. Node.js (JavaScript Runtime)**

Technical function:

- Executes JavaScript directly on your operating system (not in a browser)
- Provides system-level capabilities through core modules (fs, http, os, path, etc.)
- Uses the **V8 JavaScript Engine**
- Supports **asynchronous, event-driven** backend architecture
- Allows creation of servers, CLIs, scripts, and APIs

Key features:

- **V8 Engine**  
    Compiles JavaScript to optimized machine code (JIT compilation).
- **Core Modules**  
    Built-in libraries that interact with the OS:
    - `fs` → file system operations
    - `http` / `https` → server creation and network tasks
    - `os` → system info
    - `crypto` → hashing/encryption
    - `path` → path utilities

### **B. NPM (Node Package Manager)**

NPM is installed automatically with Node.js.

Technical role:

- Manages external libraries (“packages”)
- Downloads packages from the global NPM registry
- Handles versioning, updates, and dependencies
- Creates and manages **package.json**, the project manifest

Use cases:

- Install frameworks (Express, React, Mongoose)
- Install development tools (nodemon, ESLint)
- Install production libraries (bcrypt, multer, jwt tokens)

Key commands:

```bash
npm init 
npm install <package> 
npm uninstall <package> 
npm install --save-dev <package>
```

---

# ✅ **3. Why LTS Version Is Used**

**LTS (Long-Term Support)** versions are:

- Stable
- Recommended for production
- Receive security updates and critical fixes
- Supported longer than “Current” versions

For backend development, LTS ensures:

- Fewer breaking changes
- Higher stability
- Better compatibility with packages

---

# ✅ **4. Installation Instructions (Technical Steps)**

## **A. Windows Installation**

1. Download the `.msi` installer from [https://nodejs.org/en/download](https://nodejs.org/en/download)
2. Run the installer:
    - Accept license
    - Keep default installation path
    - Install required features
3. Do **not** enable additional tools like Chocolatey (not needed here)
4. Finish installation
![[Pasted image 20251111140052.png]]

```embed
title: "How to Download & Install Node.js on Windows | Step-by-Step Guide"
image: "https://i.ytimg.com/vi/qw7hgqssvCA/maxresdefault.jpg"
description: "Learn how to download and install Node.js on Windows in this step-by-step guide.✅ What you’ll learn in this video:How to download Node.js from the official w..."
url: "https://youtu.be/qw7hgqssvCA"
favicon: ""
aspectRatio: "56.25"
```

## **B. macOS Installation**

1. Download the `.pkg` installer
2. Run installer
3. Accept license, install, and complete the setup

```embed
title: "How to Install Node.js LTS (Long-Term Support) on Mac with Homebrew"
image: "https://i.ytimg.com/vi/7gBw-4471YM/maxresdefault.jpg"
description: "Learn how to install the LTS version of Node.js on macOS using Homebrew.📌 Key Topics Covered:- Understanding the difference between latest and LTS versions-..."
url: "https://youtu.be/7gBw-4471YM"
favicon: ""
aspectRatio: "56.25"
```

## **C. Linux Installation (Ubuntu/Debian)**

Most recommended method: **nvm** (Node Version Manager)

Steps:

```bash
sudo apt update sudo apt install curl
```

Install NVM:

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
```

Close and reopen terminal, then install Node LTS:

```bash
nvm install --lts
```

NVM allows:

- Switching Node versions
- Installing multiple versions
- Avoiding system-wide conflicts

---

# ✅ **5. Verifying Installation**

Run these commands in the terminal:

### **Check Node.js version**

```bash
node -v
```

### **Check NPM version**

```bash
npm -v
```
If both show version numbers, installation is correct.

---

# ✅ **6. The Role of `package.json`**

When you run:

```bash
npm init
```

NPM generates `package.json`.

It stores:

- Project metadata
- Installed dependencies
- Scripts
- Version info

This allows:

- Reproducible installations
- Easy collaboration
- Automated setup with `npm install`

---

# ✅ **7. Assignment Summary (Technical Steps)**

For submission:

1. Open terminal (Git Bash for Windows, Terminal for macOS/Linux)
2. Run:
    `node -v npm -v`
3. Take a screenshot with both commands visible
4. Upload screenshot

---

# ✅ **8. Summary (For Quick Revision)**

- Node.js = JavaScript runtime + V8 engine + core system modules
- NPM = package manager + dependency manager
- Install the LTS version for stability
- Use NVM on Linux for version control
- Verify installation with `node -v` and `npm -v`
- `package.json` is essential for managing project dependencies
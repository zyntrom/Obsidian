# **1.3 – Setting Up Your Development Environment**

## **Overview**

A development environment is the complete setup of tools required to write, test, and manage code efficiently.  
This section covers installing and configuring:

- **VS Code (editor)**
- **Node.js + npm (runtime + package manager)**
- **Git (version control)**
- **Essential VS Code extensions**
- **Workspace customization**
- **Package managers**
- **Verification and troubleshooting**

---

## **1. Installing Visual Studio Code (VS Code)**

### **Definition**

Visual Studio Code is a lightweight, open-source code editor by Microsoft with built-in support for JavaScript, HTML, CSS and extensions for almost every language.

### **Why It Matters**

- Supports syntax highlighting, IntelliSense, debugging, and Git.
- Customizable via extensions and settings.
- Integrates terminal, making it an all-in-one workspace.

---

### **Installation Steps**

#### **Windows**

1. Go to [https://code.visualstudio.com](https://code.visualstudio.com)
2. Download → **“Download for Windows”** (~80–90 MB).
3. Run installer → accept license → choose location.
4. **Enable these options:**
    - ✅ Add “Open with Code” to Explorer context menu
    - ✅ Register as editor for file types
    - ✅ Add to PATH (for command-line launch)
5. Click **Install**, then **Launch VS Code**.

#### **macOS**

1. Download from the same site → choose Intel or Apple Silicon build.
2. Extract `.zip`, drag app to Applications.
3. Launch VS Code.
4. Add to PATH:
    - Press `Cmd + Shift + P` → type “shell command” → choose  
        **Shell Command: Install ‘code’ command in PATH**.

#### **Linux (Ubuntu/Debian)**

**Option A – .deb package**

```bash
sudo dpkg -i code_*.deb 
sudo apt-get install -f
```

**Option B – apt repository (recommended)**

```bash
sudo apt update 
sudo apt install software-properties-common apt-transport-https wget 
wget -q https://packages.microsoft.com/keys/microsoft.asc -O- | sudo apt-key add - 
sudo add-apt-repository "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main" 
sudo apt update && sudo apt install code
```

#### **Verify**

```bash
code --version
```

---

## **2. Installing Node.js and npm**

### **Definition**

- **Node.js** – JavaScript runtime built on V8 engine; runs JS outside the browser.
- **npm (Node Package Manager)** – Installs and manages libraries, frameworks, and tools.

### **Importance**

- Powers frontend build tools (webpack, vite, babel) and backend servers (Express.js).
- npm enables dependency management and project automation.

---

### **Installation Steps**

#### **Windows**

1. Visit [https://nodejs.org](https://nodejs.org) → download **LTS (Long Term Support)** version.
2. Run `.msi` installer.
    - Check **“npm package manager”**.
    - Allow “Automatically install necessary tools”.
3. Complete setup → restart system.
4. **Verify:**
```bash
node --version npm --version
```

#### **macOS**

**Option 1 – Official Installer**

```bash
# After downloading .pkg 
node --version npm --version
```

**Option 2 – Homebrew (Recommended)**

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)" brew install node node --version npm --version
```

#### **Linux (Ubuntu/Debian)**

```bash
sudo apt update 
sudo apt install curl 
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash - 
sudo apt install -y nodejs 
node --version 
npm --version
```

---

### **Basic npm Commands**

|Purpose|Command|
|---|---|
|Check npm version|`npm --version`|
|Initialize project|`npm init` or `npm init -y`|
|Install package locally|`npm install package-name` or `npm i package-name`|
|Install dev dependency|`npm i -D package-name`|
|Install globally|`npm install -g package-name`|
|Remove package|`npm uninstall package-name`|
|Update packages|`npm update`|
|Run script from package.json|`npm run script-name`|
|Start project|`npm start`|

---

### **Understanding package.json**

A metadata file created by `npm init` that stores project info and dependencies.

Example:

`{   "name": "my-project",   "version": "1.0.0",   "scripts": {     "start": "node index.js",     "dev": "nodemon index.js"   },   "dependencies": {     "express": "^4.18.2"   },   "devDependencies": {     "nodemon": "^3.0.1"   } }`

---

## **3. Installing and Configuring Git**

### **Definition**

Git is a distributed version control system used to track code changes, collaborate with teams, and manage versions of projects.

---

### **Installation Steps**

#### **Windows**

1. Download → [https://git-scm.com/download/win](https://git-scm.com/download/win)
    
2. Run installer and choose:
    
    - Editor: **VS Code**
        
    - PATH: **Git from command line and 3rd-party software**
        
    - HTTPS: **OpenSSL library**
        
    - Line endings: **Windows-style checkout, Unix-style commit**
        
    - Terminal: **MinTTY**
        
    - Credential Helper: **Git Credential Manager**
        
3. **Install** and verify:
    
    `git --version`
    

#### **macOS**

`brew install git # or xcode-select --install git --version`

#### **Linux**

`sudo apt update sudo apt install git git --version`

---

### **Initial Configuration**

`git config --global user.name "Your Name" git config --global user.email "your.email@example.com" git config --global init.defaultBranch main git config --list`

These details are recorded with every commit and define the default branch.

---

## **4. Essential VS Code Extensions**

|Extension|Identifier|Purpose|
|---|---|---|
|**ESLint**|dbaeumer.vscode-eslint|Detects and fixes JS code issues.|
|**Prettier**|esbenp.prettier-vscode|Formats code consistently on save.|
|**Live Server**|ritwickdey.LiveServer|Runs local server with auto-reload.|
|**ES7+ React Snippets**|dsznajder.es7-react-js-snippets|Provides React and hook shortcuts.|
|**Auto Rename Tag**|formulahendry.auto-rename-tag|Syncs paired HTML tags.|
|**Path Intellisense**|christian-kohler.path-intellisense|Autocompletes file paths.|
|**GitLens**|eamodio.gitlens|Enhances Git history and blame info.|
|**Material Icon Theme**|PKief.material-icon-theme|Improves UI with file icons.|

### **Prettier Configuration**

1. Open **Settings → Search "formatter"** → select Prettier.
    
2. Enable **Format on Save**.
    
3. Optionally add to settings.json:
    

`"editor.formatOnSave": true, "editor.defaultFormatter": "esbenp.prettier-vscode"`

---

## **5. Customizing Your Workspace**

### **Integrated Terminal**

- Open terminal: `Ctrl +` (or Cmd + `).
    
- Set default terminal (profile e.g., Git Bash) via:  
    `Ctrl+Shift+P → Terminal: Select Default Profile`.
    

### **Recommended settings.json**

`{   "editor.fontSize": 14,   "editor.tabSize": 2,   "editor.wordWrap": "on",   "editor.minimap.enabled": true,   "editor.formatOnSave": true,   "editor.defaultFormatter": "esbenp.prettier-vscode",   "editor.codeActionsOnSave": { "source.fixAll.eslint": true },   "files.autoSave": "afterDelay",   "files.autoSaveDelay": 1000,   "terminal.integrated.fontSize": 13,   "emmet.includeLanguages": { "javascript": "javascriptreact" } }`

### **Keyboard Shortcuts**

|Action|Windows/Linux|macOS|
|---|---|---|
|Command Palette|Ctrl + Shift + P|Cmd + Shift + P|
|Quick Open|Ctrl + P|Cmd + P|
|Toggle Terminal|Ctrl + `|Cmd + `|

---

## **6. Understanding Package Managers**

### **Definition**

A package manager automates installation, updating, and removal of software libraries in a project.

### **npm vs Yarn**

|Feature|npm|Yarn|
|---|---|---|
|Developer|Node.js Team|Facebook|
|Speed|Slightly slower|Faster caching|
|Default with Node.js|✅ Yes|❌ Install separately|
|For this course, use **npm**.|||

---

## **7. Verification Checklist**

|Tool|Verification Command|Expected Output|
|---|---|---|
|**VS Code**|Open → `Ctrl + ``|Terminal appears inside VS Code|
|**Node.js**|`node --version`|Displays version (v20+ recommended)|
|**npm**|`npm --version`|Displays npm version|
|**Git**|`git --version` / `git config --list`|Version + user config shown|
|**Extensions**|Check Installed Tab|ESLint, Prettier, Live Server visible|

---

### **Quick Test Project**

`mkdir web-dev-test cd web-dev-test npm init -y echo '<!DOCTYPE html><html><head><title>Test</title></head><body><h1>Hello World!</h1></body></html>' > index.html code .`

In VS Code → Right-click **index.html** → **Open with Live Server** → verify “Hello World!” in browser.

---

## **8. Common Issues & Fixes**

|Issue|Cause|Fix|
|---|---|---|
|`code` command not found (macOS/Linux)|VS Code not added to PATH|Run “Shell Command: Install ‘code’ command in PATH” in Command Palette|
|`npm` commands not working (Windows)|PATH not updated|Restart PC / Reinstall Node.js with PATH option|
|`git` not recognized|PATH misconfigured during install|Reinstall Git and choose “Git from command line”|
|Live Server not launching|Non-HTML file or extension disabled|Ensure `.html` file and reload VS Code window|

---

## **9. Next Steps & Resources**

- Explore **VS Code interface** and shortcuts.
    
- Practice basic **Git commands** (`git init`, `git add`, `git commit`).
    
- Explore packages on **npmjs.com**.
    
- Try custom themes and more extensions.
    

**Documentation Links**

- VS Code Docs → [https://code.visualstudio.com/docs](https://code.visualstudio.com/docs)
    
- Node.js Docs → [https://nodejs.org/docs](https://nodejs.org/docs)
    
- npm Docs → [https://docs.npmjs.com](https://docs.npmjs.com)
    
- Git Docs → [https://git-scm.com/doc](https://git-scm.com/doc)
    

---

## **10. Summary**

✅ Installed and configured VS Code.  
✅ Installed Node.js and npm.  
✅ Installed and set up Git.  
✅ Added key VS Code extensions.  
✅ Customized workspace and terminal.  
✅ Learned npm package management.  
✅ Verified full environment functionality.

Your development environment is now ready for full-stack web development.
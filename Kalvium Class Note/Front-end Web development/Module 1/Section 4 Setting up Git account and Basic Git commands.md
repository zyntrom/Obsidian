## ✅ Summary 

This lesson walks you through the **basics of Git** and **GitHub**, including setting up your own GitHub account, initializing a local Git project, and using the **six most essential Git commands** that developers use daily. You’ll also understand how Git tracks changes and why it's important for managing your code professionally.

---

## 🧠 Key Notes

### 🌐 Setting Up Your GitHub Account

- **GitHub** is a cloud-based hosting service for version-controlled code using **Git**.
- To create an account:
    1. Go to [github.com](https://github.com)
    2. Click **Sign Up**
    3. Choose a **professional username**
    4. Use a valid email and strong password
    5. **Verify** your email

> 🔑 Tip: Your GitHub username becomes part of your developer identity, so pick something you can use professionally (e.g., no `gamer1234`).

---

### 📁 Creating a Local Git Repository


`cd Desktop mkdir my-first-repo cd my-first-repo git init`

- `git init`: Creates a hidden `.git` folder to start tracking changes in the project.
- This folder is the **control center** of Git in that directory.

---

### 📥 Cloning an Existing Repository


`git clone https://github.com/username/project-name.git`

- Downloads an existing project along with its entire history and branches to your local system.

---

### 🔺 Git Workflow Triangle

This is the basic 3-step cycle for saving changes:

1. **Stage the changes**  
    `git add filename` or `git add .`
2. **Commit the changes**  
    `git commit -m "Write a message"`
3. **Push (optional, once remote is set)**  
    This lesson doesn’t cover `git push`, but remember it's the step that sends your commits to GitHub.

---

### 📊 Tracking Progress

- **Check status**
    `git status`
    
    Tells you:
    - Which files were modified
    - What is staged and ready to commit
    - What Git is currently tracking
- **See commit history**
- 
    `git log`
    Shows:
    
    - Every past commit
    - Timestamps
    - Commit messages
    - Commit IDs

---

### 💻 Practice Example


`touch hello.txt` 
`echo "Welcome!" > hello.txt` 
`git status` 
`git add hello.txt` 
`git commit -m "Add welcome message"` 
`git log`

This full example covers the **init ➝ add ➝ commit ➝ log** flow.

---

### 📋 Quick Reference: 6 Core Git Commands

|Command|Purpose|
|---|---|
|`git init`|Start tracking a new project|
|`git clone [url]`|Download an existing project|
|`git add [file]/.`|Stage file(s) for committing|
|`git commit -m "message"`|Save a snapshot of your changes|
|`git status`|Show current file status|
|`git log`|View commit history|

---

## 🛠️ Troubleshooting Tips

|**Issue**|**Fix**|
|---|---|
|Forgot commit message|Git opens a text editor — just write the message, save and exit|
|Can't see `.git` folder|Enable “Show hidden files” in your file explorer|
|Typos in commit message|Can fix later using `git commit --amend` (covered in later lessons)|

---

## 📘 Important Points for Exams

- Git = distributed version control system.
- GitHub = online platform to host Git repositories.
- `git init` vs `git clone`: one creates a repo, the other downloads one.
- Three-step Git workflow: `add → commit → push`.
- Use `status` and `log` often to track work and history.
- `.git` folder holds all tracking data (invisible by default).
- Commit messages should be short and meaningful.
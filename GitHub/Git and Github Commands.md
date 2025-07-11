## 🧰 1. Git Setup (First Time Only)

`git config --global user.name "Your Name"` 
`git config --global user.email "your@email.com"` 
`git config --global init.defaultBranch main     # Use 'main' instead of 'master'`

Check settings:

`git config --list`

---

## 📁 2. Create and Work with a Local Git Repository

### ✅ Initialize Git repo

`git init`

### ✅ Check status

`git status`

### ✅ Add files to staging area

`git add <filename> git add .       # All files`

### ✅ Commit staged files

`git commit -m "First commit"`

### ✅ View commit history

`git log`

---

## 🌐 3. Connect to Remote GitHub Repo

### ✅ Add a remote repository

`git remote add origin https://github.com/yourusername/yourrepo.git`

Check if added:

`git remote -v`

---

## 🔁 4. Sync/Merge Local and Remote GitHub Repository

### 💥 Case 1: Remote GitHub already has commits (README, license)

#### ✅ Fetch and merge with local repo

`git fetch origin git merge origin/main --allow-unrelated-histories`

#### 🔃 Push merged repo to GitHub

`git push -u origin main`

---

### 🆕 Case 2: Brand-new GitHub repo (empty)

#### ✅ Push local repo to GitHub

`git branch -M main              # Rename current branch to main git remote add origin https://github.com/yourusername/yourrepo.git git push -u origin main`

---

## 🔀 5. Branching

### ✅ Create and switch to new branch

`git checkout -b feature-branch`

### ✅ Switch branches

`git switch main                # Or git checkout main`

### ✅ Merge branch into main

`git checkout main git merge feature-branch`

---

## 🧹 6. Clean/Discard Changes

### Discard unstaged changes:

`git checkout -- <filename>`

### Unstage a file:

`git reset <filename>`

---

## 🚀 7. GitHub Pages Hosting (HTML Website)

1. Go to your repo → Settings → Pages
2. Choose:
    - Branch: `main`
    - Folder: `/root`
3. Save → You’ll get a public link like:
    
    `https://yourusername.github.io/yourrepo/`

---

## 🛠️ 8. Other Useful Git Commands

### See list of branches

`git branch`

### Delete a branch

`git branch -d branchname`

### Stash changes temporarily

`git stash git stash pop`

### Clone a repo

`git clone https://github.com/username/repo.git`

### Pull latest changes from GitHub

`git pull`

---

## 🧾 Common Git Workflow Summary

|Action|Command|
|---|---|
|Start a project|`git init`|
|Stage and commit|`git add . && git commit -m "msg"`|
|Connect to GitHub|`git remote add origin <url>`|
|Push code|`git push -u origin main`|
|Merge remote changes|`git fetch origin && git merge origin/main`|
|Clone repo|`git clone <url>`|
|Host HTML site on GitHub Pages|GitHub → Settings → Pages|
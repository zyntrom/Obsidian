## 🧰 1. Git Setup (First Time Only)

```bash
git config --global user.name "Your Name" 
git config --global user.email "your@email.com" 
git config --global init.defaultBranch main     
# Use 'main' instead of 'master'
```

Check settings:

```bash
git config --list
```

---

## 📁 2. Create and Work with a Local Git Repository

### ✅ Initialize Git repo

```bash
git init
```

### ✅ Check status

```bash
git status
```

### ✅ Add files to staging area

```bash
git add <filename> git add .       # All files
```

### ✅ Commit staged files

```bash
git commit -m "First commit"
```

### ✅ View commit history

```bash
git log
```

---

## 🌐 3. Connect to Remote GitHub Repo

### ✅ Add a remote repository

```bash
git remote add origin https://github.com/yourusername/yourrepo.git
```

Check if added:

```bash
git remote -v
```

---

## 🔁 4. Sync/Merge Local and Remote GitHub Repository

### 💥 Case 1: Remote GitHub already has commits (README, license)

#### ✅ Fetch and merge with local repo

```bash
git fetch origin git merge origin/main --allow-unrelated-histories
```

#### 🔃 Push merged repo to GitHub

```bash
git push -u origin main
```

---

### 🆕 Case 2: Brand-new GitHub repo (empty)

#### ✅ Push local repo to GitHub

```bash
git branch -M main              
# Rename current branch to main git remote add origin https://github.com/yourusername/yourrepo.git 
git push -u origin main
```

---

## 🔀 5. Branching

### ✅ Create and switch to new branch

```bash
git checkout -b feature-branch
```

### ✅ Switch branches

```bash
git switch main                # Or 
git checkout main
```

### ✅ Merge branch into main

```bash
git checkout main git merge feature-branch
```

---

## 🧹 6. Clean/Discard Changes

### Discard unstaged changes:

```bash
git checkout -- <filename>
```

### Unstage a file:

```bash
git reset <filename>
```

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

```bash
git branch
```

### Delete a branch

```bash
git branch -d branchname
```

### Stash changes temporarily

```bash
git stash git stash pop
```

### Clone a repo

```bash
git clone https://github.com/username/repo.git
```

### Pull latest changes from GitHub

```bash
git pull
```

---

## 🧾 Common Git Workflow Summary

| Action                         | Command                                     |
| ------------------------------ | ------------------------------------------- |
| Start a project                | `git init`                                  |
| Stage and commit               | `git add . && git commit -m "msg"`          |
| Connect to GitHub              | `git remote add origin <url>`               |
| Push code                      | `git push -u origin main`                   |
| Merge remote changes           | `git fetch origin && git merge origin/main` |
| Clone repo                     | `git clone <url>`                           |
| Host HTML site on GitHub Pages | GitHub → Settings → Pages                   |

# 🧰 1. First-Time Git Setup (One-Time Only)

```bash
git config --global user.name "Your Name" 
git config --global user.email "your@email.com" 
git config --global init.defaultBranch main 
git config --global core.editor "nano"       # Use nano instead of vim
```

✅ Check setup:

```bash
git config --list
```

---

# 📁 2. Local Git Basics

|Action|Command|
|---|---|
|Initialize a repo|`git init`|
|Check status|`git status`|
|Add specific file|`git add filename.ext`|
|Add all files|`git add .`|
|Unstage a file|`git reset filename.ext`|
|Commit changes|`git commit -m "your message"`|
|See commit history|`git log`|

---

# 🔗 3. Connect to GitHub Remote

## ✅ Add Remote Repo

```bash
git remote add origin https://github.com/yourusername/yourrepo.git 
git remote -v     # Check remotes
```

---

# 🔁 4. Sync Local and Remote Repos

### Case 1: Remote GitHub already has commits (README, LICENSE)

```bash
git fetch origin 
git merge origin/main --allow-unrelated-histories 
git push -u origin main
```

### Case 2: GitHub repo is empty (New)

```bash
git branch -M main git remote add origin https://github.com/yourusername/yourrepo.git git push -u origin main
```

---

# 🔀 5. Branching & Merging

|Action|Command|
|---|---|
|Create + switch branch|`git checkout -b feature`|
|Switch to a branch|`git switch main` or `git checkout main`|
|See all branches|`git branch`|
|Merge into main|`git checkout main` → `git merge feature`|
|Delete a branch|`git branch -d branchname`|

---

# ⚔️ 6. Merge Conflicts (If Any)

- Git will **highlight conflicting lines**.
- Manually fix them in the files (look for <<<<<<<,====== ,>>>>>>>).
- After fixing:

```bash
git add conflicted-file.txt git commit    # Finalize merge
```

✅ You can avoid Vim and use Nano with:

```bash
git config --global core.editor "nano"
```

---

# 🧹 7. Discard or Stash Changes

|Action|Command|
|---|---|
|Discard unstaged changes|`git checkout -- filename`|
|Unstage a staged file|`git reset filename`|
|Stash changes temporarily|`git stash`|
|Reapply stashed changes|`git stash pop`|

---

# 🌐 8. GitHub Pages Hosting (for HTML/CSS)

1. Push your HTML files to the repo
2. Go to **GitHub → Your Repo → Settings → Pages**
3. Choose:
    
    - **Branch**: `main`
        
    - **Folder**: `/root` or `/docs`
        
4. GitHub will give you a public website link like:  
    👉 `https://yourusername.github.io/yourrepo/`
    

---

# 🚀 9. Pull / Clone / Push

|Action|Command|
|---|---|
|Pull updates|`git pull`|
|Clone a repo|`git clone <url>`|
|Push to GitHub|`git push -u origin main`|

---

# 📘 10. Common Git Workflow (Cheat Sheet)

bash

CopyEdit

`# Start a new project git init  # Work on files git add .  git commit -m "Initial commit"  # Connect to GitHub git remote add origin https://github.com/username/repo.git  # Push to GitHub git push -u origin main  # If GitHub repo already has files (README, license) git fetch origin git merge origin/main --allow-unrelated-histories git push -u origin main`

---

# 🧾 Quick Reference Table

|Task|Command|
|---|---|
|Set username/email|`git config --global user.name/email`|
|Change default editor to Nano|`git config --global core.editor "nano"`|
|See config list|`git config --list`|
|Add all files|`git add .`|
|Commit|`git commit -m "msg"`|
|Merge remote changes|`git fetch origin && git merge origin/main`|
|Create + switch to new branch|`git checkout -b newbranch`|
|Merge feature into main|`git checkout main && git merge newbranch`|
|Push to GitHub|`git push -u origin main`|
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

| Action             | Command                        |
| ------------------ | ------------------------------ |
| Initialize a repo  | `git init`                     |
| Check status       | `git status`                   |
| Add specific file  | `git add filename.ext`         |
| Add all files      | `git add .`                    |
| Unstage a file     | `git reset filename.ext`       |
| Commit changes     | `git commit -m "your message"` |
| See commit history | `git log`                      |
|                    |                                |

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
git branch -M main 
git remote add origin https://github.com/yourusername/yourrepo.git 
git push -u origin main
```

---

# 🔀 5. Branching & Merging

| Action                 | Command                                   |
| ---------------------- | ----------------------------------------- |
| Create + switch branch | `git checkout -b feature`                 |
| Switch to a branch     | `git switch main` or `git checkout main`  |
| See all branches       | `git branch`                              |
| Merge into main        | `git checkout main` → `git merge feature` |
| Delete a branch        | `git branch -d branchname`                |

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

```bash
# Start a new project 
<<<<<<< HEAD
git init  # Work on files git add .  
=======
git init  
# Work on files git add .  
>>>>>>> origin/main
git commit -m "Initial commit"  
# Connect to GitHub 
git remote add origin https://github.com/username/repo.git
#Push to GitHub 
<<<<<<< HEAD
git push -u origin main  
=======
git push -u origin main   
>>>>>>> origin/main
# If GitHub repo already has files (README, license) 
git fetch origin 
git merge origin/main --allow-unrelated-histories 
git push -u origin main
```

---

## 🧬 What Is Git Merging?

Merging means combining changes from one branch into another.

For example:

- You’re on `main`
- You want to **merge changes from `feature` branch** into `main`

---

## 🔑 Basic Git Merge Syntax:

```bash
git checkout main git merge feature
```

### ✅ This does 3 things:

1. Switches to the `main` branch
2. Merges the changes from the `feature` branch
3. Auto-merges if no conflicts, or asks you to resolve them if there are conflicts

---

## 📘 Step-by-Step: Git Merge from Command Line

### 🛠️ Step 1: View all branches

```bash
git branch
```

### 🧭 Step 2: Switch to the branch you want to merge **into**

```bash
git checkout main
```

### 🔁 Step 3: Merge the other branch (e.g., `feature`)

```bash
git merge feature
```

- If everything is clean → Git auto-merges and adds a commit
- If there are conflicts → Git will mark conflict areas in the files

---

## ⚔️ What to Do if There Are Merge Conflicts

1. Git will show `CONFLICT` markers in the affected files like:

`<<<<<<< HEAD this is from main branch ======= this is from feature branch >>>>>>> feature`

2. Edit the file and keep only what you want.
3. Then stage the resolved file:

```bash
git add <filename>
```

4. Finally, complete the merge with:

```bash
git commit
```

Git will create a “merge commit” with both branch histories.

---

## 🔎 Optional: Check Merge Info

```bash
git log --oneline --graph --all
```

Shows a nice visual of your merges.

---

## 🧽 Abort a Merge (if you want to cancel)

If the merge gets messy:

```bash
git merge --abort
```

---

## 📤 Push Merged Result to GitHub

Once your merge is done locally:

```bash
git push origin main
```

---

## 🧪 Example Workflow Summary

```bash
# Create and switch to a new feature branch 
git checkout -b feature  
# Make changes, commit them 
git add . 
git commit -m "Work on feature"  
# Switch to main 
git checkout main  
# Merge feature into main 
git merge feature  
# Push to GitHub git push origin main
```
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
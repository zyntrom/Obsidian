## ✅ Summary 

This lesson is a **hands-on practice** of essential Git commands. You’ve already learned the theory — now you're putting it into action by creating and managing a Git repository, tracking changes, and learning to ignore unnecessary files.

This is where you **build confidence** with the real Git workflow:  
`init → add → commit → status → ignore → repeat`

---

## 🧠 Key Notes

### 🧪 Setting Up Your Git Playground

```bash
mkdir git_game      # Make a new folder cd git_game        # Move into it 
git init            # Initialize a Git repository
```

- `git init`: Turns any folder into a Git-tracked project.
- Think of it as activating Git's time machine in that folder.

---

### 🧩 Challenge 1: Your First Git Snapshot

```bash
touch README.md     # Create a new file 
git add README.md   # Stage the file 
git commit -m "Initial commit: Added README.md"   # Commit with message
```

- `git add`: Adds file(s) to the **staging area** (think: "photo ready").
- `git commit -m`: Saves the snapshot to Git history with a message.

Check status:

```bash
git status
```

- Shows current file status — tracked, modified, staged, etc.

---

### 🔄 Challenge 2: Making Changes Like a Pro

Edit `README.md`:

`# Git Game This is a simple game to practice Git commands.`

Then check Git’s response:

```bash
git status
```

- Git will say `modified: README.md` — it tracks every change automatically.

---

### 💃 Challenge 3: The Add-Commit Dance (Main Workflow)


```bash
git add README.md                          # Stage changes 
git commit -m "Updated README.md content"  # Commit the update
```

After:

`git status`

- Should be a **clean working directory** → all changes committed.

📝 **Main Git Cycle**:

1. Modify file
2. Stage file → `git add`
3. Commit changes → `git commit -m`
4. Check status → `git status`

---

### 🚫 Challenge 4: The Art of Ignoring Files

Sometimes you don’t want Git to track certain files (e.g., config files, local secrets).

Steps:

```bash
touch config.txt touch .gitignore
```

Edit `.gitignore` and add:

`config.txt`

Then check:

`git status`

✅ Git will now ignore `config.txt` completely (won’t show in commits).

> 🔒 `.gitignore` = Your project's privacy policy!

---

## 📘 Commands Quick Reference

|Command|Description|
|---|---|
|`git init`|Start a Git repo in current folder|
|`git add <file>`|Stage file for commit|
|`git commit -m "message"`|Commit staged changes with a message|
|`git status`|See current tracked/untracked/modified file state|
|`touch <filename>`|Create a new empty file|
|`.gitignore`|File listing patterns Git should ignore|

---

## 💡 Pro Tip for Exams

Git isn’t just about commands — it’s about a **workflow**.

🪄 Use this real-world analogy in your answer:

> Git is like a **time machine + diary**. It lets you track every change in your project, undo mistakes, and collaborate without chaos.

You should be able to:

- Explain `git init → add → commit → status` in order
- Show how `.gitignore` is used
- Answer what `git status` reports at different stages
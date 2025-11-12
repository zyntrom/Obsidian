## **1.4 – Git & GitHub Fundamentals (Commits, Branches)**

**Goal:** Understand how to version, organize, and collaborate on code using Git and GitHub.

---

### 🧩 **1. What is Git?**

**Definition:**  
Git is a **Version Control System (VCS)** that tracks every change made to your code.  
It lets you:

- Save multiple versions of a project.
- Revert to older versions anytime.
- Work with others without overwriting each other’s work.

**Analogy:**  
Think of Git as an _infinite time machine for your code._

**Key Benefits:**

- Full history of your project.
- Ability to restore older versions.
- Smooth collaboration between developers.

---

### 🌐 **2. What is GitHub?**

**Definition:**  
GitHub is a **cloud-based hosting platform** for Git repositories.  
It acts as your online storage + collaboration hub.

**Purpose:**

- Backup your code online.
- Collaborate via Pull Requests.
- Share your work publicly or privately.

**Git = tool (local)**  
**GitHub = service (remote)**

---

### ⚙️ **3. Local Repository vs. Remote Repository**

|Type|Location|Description|Example Commands|
|---|---|---|---|
|**Local Repo**|Your computer|Where you create, edit, and commit code|`git init`, `git add`, `git commit`|
|**Remote Repo**|GitHub|Online version of your repo for sharing and backup|`git push`, `git pull`, `git clone`|

---

## **4. Setting Up a Local Git Repository**

### **Step 1: Initialize Git**

Transform a normal folder into a Git repository.

```bash
mkdir hello-architect 
cd hello-architect 
git init
```

**Result:** Creates a hidden `.git` folder → Git starts tracking changes.

---

## **5. The Three Git Areas**

Git manages files in three main areas:

|Area|Description|Command|
|---|---|---|
|**Working Directory**|Where you make actual file changes.|–|
|**Staging Area (Index)**|Where selected files are prepared for commit.|`git add <file>`|
|**Repository (Local Repo)**|Where committed snapshots are permanently stored.|`git commit`|

**Command to check status:**

```bash
git status
```

Shows which files are untracked, staged, or committed.

---

### 🧱 **Example: First Commit Process**

#### 1. Create a file

```bash
echo "Hello Architect!" > README.md
```

Check status:

```bash
git status
```

→ shows `README.md` as untracked.

#### 2. Stage the file

```bash
git add README.md
```

Now the file moves to the **staging area**.

#### 3. Commit the snapshot

```bash
git commit -m "Create README.md with initial project description"
```

This saves the snapshot permanently to your local repository.

#### 4. View Commit History

```bash
git log
```

Shows author, date, commit message, and unique commit ID.

---

## **6. Branches – Working in Parallel**

### **What is a Branch?**

A **branch** is an independent line of development — like creating a copy of your code to work on without affecting the main version.

- Default branch: `main`
- Use branches to add new features or test ideas safely.

**Diagram:**

```bash
main  → stable project feature/login → experiment branch
```

### **Branch Commands**

|Task|Command|Description|
|---|---|---|
|Create new branch|`git branch <branch-name>`|Makes a new branch|
|Switch branch|`git checkout <branch-name>`|Moves to that branch|
|Create + Switch|`git checkout -b <branch-name>`|Both at once|
|View all branches|`git branch`|Lists all local branches|
|Merge branch|`git merge <branch-name>`|Combines branch changes into current one|
|Delete branch|`git branch -d <branch-name>`|Removes branch|

---

### 🧪 **Example: Feature Branch Workflow**

#### 1. Create and switch to a new branch:

```bash
git checkout -b add-greeting-feature
```

#### 2. Add a file and commit:

```bash
echo "Hello everyone!" > greeting.txt 
git add greeting.txt 
git commit -m "feat: Add greeting.txt file for new feature"
```

#### 3. Switch back to main:

```bash
git checkout main
```

The `greeting.txt` disappears — it only exists on the other branch!

#### 4. Merge feature branch back:

```bash
git merge add-greeting-feature
```

Now `greeting.txt` appears again — merged into `main`.

---

## **7. Pushing Code to GitHub (Remote Repository)**

### **Step 1: Create an Empty Repository on GitHub**

- Go to **GitHub → New Repository**
- Name it `hello-architect`
- **Do not** add README or .gitignore (we already have them locally)
- Click **Create Repository**

---

### **Step 2: Connect Local Repo to GitHub Remote**

Copy your repo’s HTTPS URL from GitHub, then:

```bash
git remote add origin https://github.com/<username>/hello-architect.git`
```

Verify:

```bash
git remote -v
```

---

### **Step 3: Push to Remote**

```bash
git push -u origin main
```

**Result:**  
Your local commits are uploaded to GitHub — visible on your repository page.

---

## **8. Common Git Commands Summary**

|Command|Purpose|
|---|---|
|`git init`|Initialize a new local Git repository|
|`git add <file>`|Stage file(s) for commit|
|`git commit -m "<message>"`|Save staged files as a snapshot|
|`git status`|Show current state of repo|
|`git log`|Show commit history|
|`git branch`|List all branches|
|`git checkout <branch>`|Switch branches|
|`git merge <branch>`|Merge another branch into current|
|`git remote add origin <url>`|Link local repo to GitHub|
|`git push -u origin main`|Push commits to remote repository|

---

## **9. Professional Git Workflow (Daily Use)**

1. `git pull` → Sync your local repo with the latest version.
2. `git checkout -b feat/<feature-name>` → Start a new feature branch.
3. Make and test changes.
4. `git add .` → Stage your changes.
5. `git commit -m "feat: add login validation"` → Save a snapshot.
6. `git push origin feat/<feature-name>` → Push the branch online.
7. Create a **Pull Request** on GitHub to merge it into main.

---

## **10. Summary (Core Takeaways)**

|Concept|Summary|
|---|---|
|**Git**|Version control tool for tracking and managing code changes locally.|
|**GitHub**|Cloud-based platform for storing and sharing Git repositories.|
|**Commit**|A permanent snapshot of project files.|
|**Branch**|A separate workspace for safe, isolated development.|
|**Remote**|Online copy of your repo for collaboration.|
|**Push/Pull**|Send or receive changes between local and remote repos.|
|**Workflow**|init → add → commit → push → branch → merge|

---

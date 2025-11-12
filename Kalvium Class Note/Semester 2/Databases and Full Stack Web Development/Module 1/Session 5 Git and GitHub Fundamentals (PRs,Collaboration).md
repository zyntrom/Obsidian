# 🧠 **Module 1.5 — Git & GitHub Fundamentals (Pull Requests & Collaboration)**

---

## 📘 **1. Introduction: Collaboration Challenges**

### ❌ The "Group Project" Nightmare

When working in teams, unstructured collaboration leads to chaos:

- **Emailing files** loses commit history and context.
- **Sharing passwords** is risky and can break main code.
- **Merge conflicts** happen if multiple people edit the same file.

💡 **Solution:** Use **Pull Requests (PRs)** — a safe, review-based process to propose, discuss, and merge code changes.

---

## 🏗️ **2. What is a Pull Request (PR)?**

A **Pull Request** is a **formal proposal** to merge code from one branch (usually a feature branch) into another (usually the main branch).

Think of it as:

> “Hey team, I’ve built something on a separate branch. Can you review it before it becomes part of the main project?”

```embed
title: "Git Github Tutorial 10: What is Pull Request?"
image: "https://i.ytimg.com/vi/e3bjQX9jIBk/maxresdefault.jpg"
description: "In this git github tutorial, we will learn what is pull request and step by step guide on how to create and merge pull request.  Pull requests have become ve..."
url: "https://youtu.be/e3bjQX9jIBk"
favicon: ""
aspectRatio: "56.25"
```

---

### 🏛️ **Analogy: The Architectural Blueprint Review**

|Role|Analogy|In Git Terms|
|---|---|---|
|🧑‍🎓 Apprentice Architect|Creates a new design copy|Developer creates a **feature branch**|
|🧑‍🏫 Lead Architect|Reviews proposed design|Maintainer reviews the **Pull Request**|
|🏢 Master Blueprint|Final approved design|The **main branch** in GitHub|

🧩 The PR is like submitting your blueprint for approval before it becomes part of the master plan.

---

## ⚙️ **3. Creating a Pull Request — Step-by-Step**

We’ll simulate being both the **contributor** and the **maintainer**.

---

### 🧑‍💻 **Step 1: Contributor’s Work (Feature Branch)**

1. Make sure main is updated
    `git checkout main git pull origin main`
2. Create a new branch
    `git checkout -b add-greeting-feature`
3. Add a new file and commit
```bash
echo "Hello, from a feature branch! This is a proposed change." > greeting.txt 
git add greeting.txt 
git commit -m "feat: Add greeting.txt for new feature"
```

At this point — your new branch and commit exist **only locally**.

---

### ☁️ **Step 2: Push Branch to GitHub**

Send your branch to the remote repository:

```bash
git push origin add-greeting-feature
```

✅ Verify on GitHub → you should now see your **new branch** alongside `main`.

---

### 📨 **Step 3: Open a Pull Request**

On GitHub:

1. Click **“Compare & pull request.”**
2. Confirm the direction:  
    `base: main ← compare: add-greeting-feature`
3. Add a clear **title** and **description**.

**Example PR description:**

> This PR introduces a new `greeting.txt` file as part of our initial feature development.  
> **Changes:**
> 
> - Created `greeting.txt` with a sample message.
> 
> Ready for review ✅

4. Click **Create Pull Request**.  
    You’ve officially started the review conversation.

---

### 👀 **Step 4: Review and Merge Process**

You (or a team member) now act as the **maintainer** reviewing the PR.

#### 🔍 Pull Request Interface:

- **Conversation Tab:** Discuss changes & add feedback.
- **Commits Tab:** Shows all commits made in the PR.
- **Files Changed Tab:** Line-by-line diff view to review new code.

#### ✅ If everything looks good:

1. Click **“Merge Pull Request.”**
2. Confirm with **“Confirm Merge.”**
3. Optionally, **delete the feature branch** to keep things clean.

🧠 _Behind the scenes:_ GitHub performs a safe merge, adding your commits to the main branch’s history.

---

### 🧹 **Step 5: Sync Your Local Repository**

After merging, your local `main` branch is **out of date**.

1. Switch to main:
    `git checkout main`
2. Pull the latest updates:
    `git pull origin main`

Now `greeting.txt` will appear locally — your main branch is synced.

---

## 🔄 **4. The Complete Professional Workflow**

### 🧩 The 8-Step Collaboration Cycle

1. **Get latest main branch** → `git pull origin main`
2. **Create a feature branch** → `git checkout -b branch-name`
3. **Make changes & commit** → `git add`, `git commit`
4. **Push branch to GitHub** → `git push origin branch-name`
5. **Open Pull Request** → Describe and submit your proposal
6. **Review & discuss** → Add feedback in PR comments
7. **Merge to main** → After approval
8. **Sync local repo** → `git checkout main`, `git pull origin main`

---
```embed
title: "How Git Works: Explained in 4 Minutes"
image: "https://i.ytimg.com/vi/e9lnsKot_SQ/maxresdefault.jpg"
description: "Get a Free System Design PDF with 158 pages by subscribing to our weekly newsletter: https://bytebytego.ck.page/subscribeGit MERGE vs REBASE: Everything You ..."
url: "https://youtu.be/e9lnsKot_SQ"
favicon: ""
aspectRatio: "56.25"
```

## 🧠 **5. Key Takeaways**

|Concept|Meaning|
|---|---|
|**Branching**|Create isolated environments for development|
|**Pull Request**|A formal, review-based merge proposal|
|**Code Review**|Team process to ensure code quality and prevent bugs|
|**Merge**|Safely integrate approved code|
|**Sync Local Repo**|Keep your computer updated with GitHub’s latest code|

---

## 🏁 **6. Summary**

- Pull Requests = **collaboration with control**.
- Always **branch → commit → push → PR → merge → pull**.
- The PR workflow ensures **transparency**, **accountability**, and **quality**.
- This is the **professional standard** followed by teams worldwide.
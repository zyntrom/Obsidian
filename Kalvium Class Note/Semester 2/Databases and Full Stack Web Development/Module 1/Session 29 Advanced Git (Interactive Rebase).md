# 🧠 **1.29 — Advanced Git: Interactive Rebase**

---

## 📘 **Overview**

As projects grow, your Git commit history can become **cluttered with small, repetitive, or unclear commits**.  
**Interactive Rebase (`git rebase -i`)** helps you **rewrite and clean your commit history** so it tells a **clear, professional story** — where every commit represents one meaningful, complete change.

---

## 🎯 **Goal**

To use **interactive rebase** to:

- Combine small “Work in Progress” commits into a single, clean one
- Fix or rewrite commit messages
- Reorder commits for logical clarity
- Maintain a **professional, easy-to-read Git history**
```embed
title: "Learn Git Squash in 3 minutes // explained with live animations!"
image: "https://i.ytimg.com/vi/V5KrD7CmO4o/maxresdefault.jpg"
description: "40+ additional videos at https://learngit.io/--I'll show you how to combine commits using Git's squash tool. Squash is one of several tools available under G..."
url: "https://youtu.be/V5KrD7CmO4o"
favicon: ""
aspectRatio: "56.25"
```

```embed
title: "Learn Git Rebase in 6 minutes // explained with live animations!"
image: "https://i.ytimg.com/vi/f1wnYdLEpgI/maxresdefault.jpg"
description: "40+ additional Git lessons: https://learngit.io/Newsletter readers get my videos early: https://newsletter.themoderncoder.com/----LINKSWritten rebase referen..."
url: "https://youtu.be/f1wnYdLEpgI"
favicon: ""
aspectRatio: "56.25"
```

---

## ⚙️ **What Is Interactive Rebase?**

### ➤ Definition

`git rebase -i` (interactive rebase) allows developers to:

- **Edit**, **combine**, or **reorder** commits
- **Reword** messages for clarity
- Create a **linear, meaningful history** before sharing code

It’s like a **video editor** for your commit timeline — you can trim, merge, or rearrange clips (commits) before publishing.

---

## 🧠 **Key Operations in Interactive Rebase**

|**Operation**|**Command Keyword**|**Purpose**|
|---|---|---|
|Keep a commit|`pick`|Leave the commit unchanged|
|Combine with previous commit|`squash` or `s`|Merge multiple commits into one|
|Edit commit message|`reword` or `r`|Fix typos or improve clarity|
|Reorder commits|Move lines up/down|Change commit sequence|

---

## 🧩 **Starting an Interactive Rebase**

Command syntax:

```bash
git rebase -i HEAD~N
```

- **`HEAD~N`** → Number of commits back from the latest one you want to modify.
- Example:
```bash
git rebase -i HEAD~3
```
    Edits the last 3 commits.

This opens a text editor showing your recent commits (oldest at the top).

---

## 🧱 **Outcome 1 — Combining Commits with Squash**

### 🧩 Example Git Log (Before)

```bash
commit 5b1d3f9 Add footer link
commit 1a2b3c4 Style the new footer
commit 9d8e7f6 Add footer section

```

These 3 commits represent one single feature: “Add Footer.”

---

### 🪄 **Step-by-Step Squashing Process**

**Step 1 — Start the rebase**

```bash
git rebase -i HEAD~3
```

**Step 2 — Give Git instructions**

Editor opens:

```
pick 9d8e7f6 Add footer section
pick 1a2b3c4 Style the new footer
pick 5b1d3f9 Add footer link
```

Change to:

```bash
pick 9d8e7f6 Add footer section
squash 1a2b3c4 Style the new footer
squash 5b1d3f9 Add footer link
```

✅ Meaning: Keep the first commit, merge the next two into it.

---

**Step 3 — Write a new combined commit message**

Git now opens a second editor:

```bash
# This is a combination of 3 commits.
Add footer section
Style the new footer
Add footer link
```

Replace it with a single clean message:

```
feat: Add styled footer with social media links
```

---

### ✅ **Resulting History**

```
commit 7a8b9c0 feat: Add styled footer with social media links
```

Now one professional, clear commit replaces the messy set.

---

## 📝 **Outcome 2 — Editing Commit Messages with Reword**

If you only need to fix or clarify a message (not merge commits):

### 🧩 Example

```
commit 1a2b3c4 fix: addd login form validation
```

### 🪄 **Rewording Process**

**Step 1 — Start the rebase**

```bash
git rebase -i HEAD~1
```

**Step 2 — Change `pick` to `reword`**

```
reword 1a2b3c4 fix: addd login form validation
```

**Step 3 — Edit the message**  
Git opens another editor. Correct the typo:

```
fix: Add login form validation
```

✅ Your message is now clean and professional.

---

## ⚠️ **Outcome 3 — The Golden Rule of Rebasing**

> **Never rebase commits that have been pushed to a shared/public branch.**

### Why?

- Rebase **rewrites history**.
- It deletes old commits and creates new ones.
- If others have based their work on the old commits, rebasing will cause **conflicting histories** and **complex merge errors** for everyone.

---

### ✅ Safe vs ❌ Unsafe Rebase

|**Situation**|**Safe?**|**Reason**|
|---|---|---|
|Rebasing your **local feature branch** before merge|✅|No one else has seen it|
|Rebasing the **main/develop** branch|❌|Others already depend on it|
|Rebasing a **shared branch** after push|❌|Changes published history|

> **Rule of Thumb:**  
> “Rebase your own work; never rebase shared work.”

---

## 🧪 **Lab Example — Cleaning a Messy History**

### Given Git Log

```bash
commit 333c3c3 "oops forgot a file"
commit 222b2b2 "wip on nav"
commit 111a1a1 "started nav bar"
```

---

### **Step 1 — Start Interactive Rebase**

```bash
git rebase -i HEAD~3
```

### **Step 2 — Combine Commits**

```bash
pick 111a1a1 started nav bar
squash 222b2b2 wip on nav
squash 333c3c3 oops forgot a file
```
### **Step 3 — Final Clean Message**

```
feat: Add responsive navigation bar
```

✅ **Result:** One neat commit summarizing the feature.

---

## 🧭 **Key Takeaways**

|**Concept**|**Purpose**|**Command Example**|
|---|---|---|
|Interactive Rebase|Edit commit history|`git rebase -i HEAD~N`|
|Squash|Combine commits|Change `pick` → `squash`|
|Reword|Edit message|Change `pick` → `reword`|
|Safe Rebase|On local feature branch|✅|
|Unsafe Rebase|On shared/public branch|❌|

---

## 💡 **Best Practices**

1. Always **backup or branch** before rebasing.
2. Use **squash** to group “Work in Progress” commits into one final commit per feature.
3. Use **reword** for minor message improvements.
4. **Never** rebase commits others may already have pulled.
5. Keep commit messages **clear, imperative, and meaningful**.

---

## 📚 **References**

- Git Documentation – Interactive Rebase
- Atlassian Git Tutorials – _“Rewriting History with Rebase”_
- Pro Git Book, Chapter 3.6 – _Git Tools: Rewriting History_
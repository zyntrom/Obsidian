## ✅ Summary 

This lesson dives into **advanced Git concepts** such as **branching, merging, merge conflicts, and viewing commit history with `git log`**. These skills are crucial when collaborating with others or managing multiple features in the same project.

---

## 🧠 Key Notes

### 🌿 Branching: Creating Parallel Universes

- **Branch**: A separate line of development.
- Useful when working on new features without affecting the main code.

#### 📌 Commands:

`git branch <branch_name>       # Create a branch` 
`git checkout <branch_name>     # Switch to a branch` 
`git checkout -b <branch_name>  # Create and switch in one step` 
`git branch                     # List all branches (* shows current)`

> 📘 Analogy: Branches are like creating alternate timelines where you can safely experiment.

---

### 🔀 Merging: Bringing Branches Together

Merging integrates changes from one branch (like a feature branch) into another (usually `main`).

#### 📌 Commands:

`git checkout main              # Switch to main branch git merge <branch_name>        # Merge the branch into main`

- **Fast-forward merge**: When the target branch has no new commits, Git just moves the pointer.
- **True merge**: When both branches have diverged; Git creates a _merge commit_.

---

### ⚠️ Merge Conflicts: When Timelines Collide

Conflicts happen when two branches have conflicting changes in the same file.
#### 🛠 Identifying Conflicts:

`git status`

Shows files that are both modified.

#### 🛠 Conflict Markers in Code:

`<<<<<<< HEAD Code from current branch ======= Code from the branch you're merging >>>>>>> new-feature`

#### 🛠 Steps to Resolve:

1. Open the file and manually edit the conflicting sections.
2. Remove the conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`).
3. Stage the file:
    `git add <file>`
    
4. Complete the merge:
    
    bash
    
    CopyEdit
    
    `git commit`
    

> 💡 Tip: Always **test** your code after resolving conflicts to make sure everything works.

---

### 🕒 `git log`: View Project History

View all previous commits to understand your project's timeline.

#### 📌 Command:

bash

CopyEdit

`git log`

Shows:

- Commit hash (ID)
    
- Author
    
- Date and time
    
- Commit message
    

> 🧭 Use this to trace back changes, who made them, and when.

---

## 🧰 Git Quick Reference (New Commands in This Lesson)

|Command|Purpose|
|---|---|
|`git branch <name>`|Create a new branch|
|`git checkout <name>`|Switch to an existing branch|
|`git checkout -b <name>`|Create and switch to a new branch|
|`git merge <branch>`|Merge another branch into the current one|
|`git status`|Show file status (conflicts, changes, staged)|
|`git log`|Show commit history|
|`git add <file>`|Stage a resolved conflict file|
|`git commit`|Finalize a merge after conflict resolution|

---

## 📘 Exam-Focused Concepts to Remember

- Branching allows safe, parallel development.
    
- Use `git checkout -b` to quickly start working on new features.
    
- Merging brings branches together. Understand the difference between fast-forward and true merges.
    
- Merge conflicts are common — know how to identify and resolve them.
    
- `git log` helps track and explain project changes.
    
- Know the **merge conflict markers** (`<<<<<<<`, `=======`, `>>>>>>>`).
    

---
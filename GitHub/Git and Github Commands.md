# Git Commands - Complete reference notes

## 1. Basic Setup & configuration 

* Set username and email :

```bash
git config --global user.name "Your Name"
git config --global user.email "your@example.com"
```

* Check current config:

```bash
git cofig --list
```

* Set default branch name

```bash
git config --global init.defaultBranch main
```

* Change editor

```bash
git config --global core.editor "nano"
```

* View Specific config

```bash
git config user.name
git config core.editor
```

## Initialization & Cloning

* Create a new repo in current folder:

```bash
git init
```

* Create a new repo in specific folder

```bash
git init my-project
```

* Clone a remote repository:

```bash
git clone https://github.com/user/repo.git
git clone git@github.com:user/repo.git (SSH)
```

* Clone into a specific directory name:

```bash
git clone https://github.com/user/repo.git new-folder
```

## 3. STAGING & COMMITTING CHANGES

* Check repo status (untracked, modified, staged):

```bash
git status
```

* Add file(s) to staging area:

```bash
git add filename  
git add folder/  
git add . (all changes)
```

- Unstage a file (keep changes):  

```bash
git reset filename
```

- Commit changes with message:  

```bash
git commit -m "Commit message"
```

- Commit all tracked files directly:  

```bash
git commit -am "Message"
```

- Amend the last commit (edit message or add files):  

```bash
git commit --amend
```

## 4. VIEWING HISTORY

- Show commit history:  

```bash
git log
```

- Compact one-line log:  

```bash
git log --oneline
```

- Show graph view:  

```bash
git log --oneline --graph --all
```

- Show specific file history:  

```bash
git log filename
```

- Show changes made in a commit:  

```bash 
git show commit_id
```
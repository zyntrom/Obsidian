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

## 5. BRANCHING & MERGING

- List branches:

```bash
git branch
```

- Create new branch:

```bash
git branch branch_name
```

- Switch branch:

```bash
git checkout branch_name
#(Or new way → git switch branch_name)
```

- Create & switch to new branch:

```bash
git checkout -b new_branch
#(Or → git switch -c new_branch)
```

- Rename current branch:

```bash
git branch -m new_name
```

- Merge branch into current:

```bash
git merge branch_name
```

- Abort a merge in progress:

```bash
git merge --abort
```

- Delete branch:

```bash
git branch -d branch_name
#(force delete → -D)
```

## 6. REMOTE REPOSITORIES

- Show remotes:

```bash
git remote -v
```

- Add new remote:

```bash
git remote add origin https://github.com/user/repo.git
```

- Rename remote:

```bash
git remote rename oldname newname
```

- Remove remote:

```bash
git remote remove origin
```

- Fetch all branches from remote:

```bash
git fetch origin
```

- Push local branch to remote:

```bash
git push origin branch_name
```

- Push all branches:

```bash
git push --all origin
```

- Pull changes from remote:

```bash
git pull origin branch_name
```

- Set upstream (for tracking):

```bash
git push -u origin branch_name
```

##  7. UPDATING & SYNCHRONIZING

- Fetch latest changes (no merge):  

```bash
git fetch
```

- Merge fetched branch:  

```bash
git merge origin/main
```

- Pull = fetch + merge:  

```bash
git pull
```

- Rebase on top of latest main branch:  

```bash
git fetch origin  
git rebase origin/main
```

- Cancel rebase:  

```bash
git rebase --abort
```

- Continue rebase after fixing conflicts:  

```bash
git rebase --continue
```

🧹 8. UNDOING CHANGES

Unstage file:
git reset filename

Discard uncommitted changes:
git checkout -- filename

Undo last commit (keep changes):
git reset --soft HEAD~1

Undo last commit (discard changes):
git reset --hard HEAD~1

Revert a specific commit (create opposite commit):
git revert commit_id

Clean untracked files:
git clean -f
(clean directories too → git clean -fd)
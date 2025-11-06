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

##  8. UNDOING CHANGES

- Unstage file:  

```bash
git reset filename
```

- Discard uncommitted changes:  

```bash
git checkout -- filename
```

- Undo last commit (keep changes):  

```bash
git reset --soft HEAD~1
```

- Undo last commit (discard changes):  

```bash
git reset --hard HEAD~1
```

- Revert a specific commit (create opposite commit):  

```bash
git revert commit_id
```

- Clean untracked files:  

```bash
git clean -f  
#(clean directories too → git clean -fd)
```

## 9. STASHING WORK

- Stash current changes:

```bash
git stash
```

- Stash with a message:

```bash
git stash push -m "work in progress"
```

- List stashes:

```bash
git stash list
```

- Apply latest stash:

```bash
git stash apply
```

- Apply specific stash:

```bash
git stash apply stash@{1}
```

- Remove latest stash:

```bash
git stash drop
```

- Clear all stashes:
- git stash clear

Create and switch to new branch from stash:
git stash branch new_branch_name

🧭 10. TAGGING

List tags:
git tag

Create tag:
git tag v1.0

Create tag with message (annotated):
git tag -a v1.0 -m "Version 1.0 release"

Push all tags to remote:
git push origin --tags

Delete tag locally:
git tag -d v1.0

Delete tag remotely:
git push origin --delete tag v1.0

🧰 11. INSPECTING & COMPARING

Compare working directory with last commit:
git diff

Compare staged with last commit:
git diff --staged

Compare two commits:
git diff commit1 commit2

Show which commit introduced a line:
git blame filename

Show who changed what and when (detailed blame):
git annotate filename

🧩 12. REMOTE TROUBLESHOOTING & FIXES

Force push changes:
git push origin branch_name --force

Pull with rebase (clean history):
git pull --rebase

Change remote URL:
git remote set-url origin https://github.com/user/new_repo.git

Prune deleted remote branches:
git fetch -p

🧱 13. SUBMODULES (for nested repos)

Add submodule:
git submodule add https://github.com/user/lib.git
 libs/libname

Init and update submodules:
git submodule update --init --recursive

Update submodules to latest commit:
git submodule update --remote

Remove submodule:

Delete the entry from .gitmodules

Run → git rm --cached path/to/submodule

Delete folder manually

🧮 14. PATCHES & EXPORTING

Create patch file:
git format-patch -1 commit_id

Apply patch file:
git apply patchfile.patch

Archive repo as zip/tar:
git archive --format=zip HEAD > repo.zip

🧩 15. DEBUGGING & MAINTENANCE

Check repository integrity:
git fsck

Optimize local repo:
git gc --prune=now --aggressive

Find broken references:
git reflog

Recover deleted commits:
git reflog
git checkout commit_id

🧾 16. ALIASES (SHORTCUT COMMANDS)

Set alias example:
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.cm "commit -m"
git config --global alias.st status

Use alias:
git co main
git cm "message"

⚡ 17. MISCELLANEOUS USEFUL COMMANDS

List ignored files:
git status --ignored

List tracked files:
git ls-files

Check current branch:
git branch --show-current

See remotes and branches:
git remote show origin

Show current HEAD commit:
git rev-parse HEAD

Show current branch’s upstream:
git rev-parse --abbrev-ref --symbolic-full-name @{u}
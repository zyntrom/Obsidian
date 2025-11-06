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


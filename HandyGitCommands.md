# 🧰 Git Daily Command Reference 

A practical, easy-to-read guide for the most common Git operations — neatly grouped by category.

---

## ⚙️ 1. Setup & Repository Basics

| Purpose | Command |
|----------|----------|
| Configure username | `git config --global user.name "Your Name"` |
| Configure email | `git config --global user.email "you@example.com"` |
| View configuration | `git config --list` |
| Clone an existing repository | `git clone https://github.com/user/repo.git` |
| Initialize a new repository | `git init` |
| Check current branch | `git branch --show-current` |
| Check repo status | `git status` |

---

## 🌿 2. Branch Management

| Purpose | Command |
|----------|----------|
| View local branches | `git branch` |
| View remote branches | `git branch -r` |
| Create a new branch | `git checkout -b feature-branch` |
| Switch to another branch | `git checkout qa/2.x` |
| Set upstream tracking | `git branch --set-upstream-to=origin/qa/2.x qa/2.x` |
| Delete a local branch | `git branch -d feature-branch` |
| Delete a remote branch | `git push origin --delete feature-branch` |

---

## ✏️ 3. Staging & Committing

| Purpose | Command |
|----------|----------|
| Stage one file | `git add filename.ext` |
| Stage all files | `git add .` |
| Unstage a file | `git reset HEAD filename.ext` |
| Commit with message | `git commit -m "Describe your change"` |
| Amend last commit | `git commit --amend` |
| View commit history (simple) | `git log --oneline --graph --decorate` |

---

## 🔄 4. Syncing with Remote

| Purpose | Command |
|----------|----------|
| Fetch remote updates | `git fetch origin` |
| Pull updates into current branch | `git pull` |
| Pull specific branch | `git pull origin qa/2.x` |
| Push local commits | `git push` |
| Push with upstream (first time) | `git push -u origin feature-branch` |
| Check remote URLs | `git remote -v` |
| Change remote URL | `git remote set-url origin git@github.com:user/repo.git` |

---

## 🧹 5. Undoing / Fixing Mistakes

| Purpose | Command |
|----------|----------|
| Discard local file changes | `git checkout -- filename.ext` |
| Undo last commit but keep changes | `git reset --soft HEAD~1` |
| Undo last commit and changes | `git reset --hard HEAD~1` |
| Reset to match remote branch (⚠️ overwrites local) | `git fetch origin && git reset --hard origin/qa/2.x` |
| Remove untracked files | `git clean -fd` |

---

## 🧪 6. Temporary Work (Stashing)

| Purpose | Command |
|----------|----------|
| Stash current changes | `git stash` |
| List stashed changes | `git stash list` |
| Apply last stash | `git stash pop` |
| Drop last stash | `git stash drop` |

---

## 🔍 7. Inspection & Logs

| Purpose | Command |
|----------|----------|
| Show commit history | `git log --oneline --graph --decorate` |
| Show detailed commit history | `git log -p` |
| Show file changes | `git diff` |
| Show who changed a line | `git blame filename.ext` |
| View branch tracking info | `git branch -vv` |


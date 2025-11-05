# Git Interactive Rebase vs Reset

When working with Git, you often need to clean up your commits or undo changes. Two common commands for this are **`git rebase -i`** and **`git reset`**. They work differently and serve different purposes.

---

## 1️⃣ `git rebase -i HEAD~5` (Interactive Rebase)

**Purpose:**  
Rewrites the last N commits (here, the last 5 commits). You can **reorder, squash, edit, or remove commits**.

**How it works:**  

```bash
git rebase -i HEAD~5

Opens an editor showing the last 5 commits, for example:

pick 123abc Commit message 1
pick 456def Commit message 2
pick 789ghi Commit message 3
pick 012jkl Commit message 4
pick 345mno Commit message 5
```

**You can replace pick with:**

**edit** → change the commit

**squash** → combine this commit with the previous one

**drop** → remove the commit

**reword** → edit the commit message

After saving, Git reapplies the commits in the new order or with modifications, effectively rewriting history.

**Key Points:**

Only affects commits in your current branch.

History is rewritten, so if commits were already pushed, you may need to force push:

**git push -f**


Useful for cleaning up your commit history before sharing your work.

2️⃣ git reset
---
**Purpose:**
Moves the HEAD of your branch to a previous commit. You can optionally keep or discard changes in the working directory or staging area.

Common forms:

**Soft reset**

git reset --soft HEAD~3


Moves HEAD back 3 commits.

Keeps changes staged.

Good for “uncommitting” commits but keeping changes ready to recommit.

**Mixed reset (default)**

git reset HEAD~3


Moves HEAD back 3 commits.

Keeps changes in the working directory, but unstages them.

Useful to redo commits.

**Hard reset**

git reset --hard HEAD~3


Moves HEAD back 3 commits.

Discards all changes in the working directory and staging area.

Dangerous if you have uncommitted work.

## 🔍 Key Differences Between `git rebase -i` and `git reset`
---
| **Feature**          | **`git rebase -i`**                          | **`git reset`**                           |
|----------------------|---------------------------------------------|-------------------------------------------|
| **Purpose**          | Rewrite last N commits interactively         | Move HEAD to a previous commit            |
| **Scope**            | Specific number of commits                   | From current commit to any previous commit |
| **Working Directory**| Mostly unchanged                             | Can keep, unstage, or discard changes     |
| **History**          | Rewrites commit history                      | Moves branch pointer, may discard commits |
| **Use Case**         | Clean up commits before pushing              | Undo commits, redo commits, discard changes |

Visual Intuition
---
Before:
A - B - C - D - E (HEAD)

Interactive rebase:
- Can reorder, squash, edit, or drop commits
- History rewritten

Reset --soft HEAD~2:
- HEAD moves back 2 commits
- Changes from D & E stay staged

Reset --mixed HEAD~2:
- HEAD moves back 2 commits
- Changes unstaged

Reset --hard HEAD~2:
- HEAD moves back 2 commits
- Changes discarded

Summary
---
git rebase -i → Edit, squash, reorder, or clean up commits in your branch.

git reset → Move HEAD to a previous commit; choose what happens to staged and working directory changes (soft, mixed, hard).

Both are powerful tools — use carefully, especially if commits were already pushed.


---

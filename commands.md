# Git Commands Reference Guide

This document provides a comprehensive list of useful Git commands for working on a project. It includes basic operations, error handling, restoring changes, conflict resolution, and advanced workflows.

---

## 🧰 Basic Git Workflow

| Command                      | Purpose                                              |
|-----------------------------|------------------------------------------------------|
| `git clone <repo-url>`      | Clone a remote repository locally.                   |
| `git pull`                  | Fetch and merge latest changes from remote branch.   |
| `git push`                  | Push local commits to the remote repository.         |
| `git commit -m "message"`   | Commit staged changes with a descriptive message.    |
| `git status`                | Show current state of working directory/staging area.|

---

## 🔁 Branch Management

| Command                          | Purpose                                    |
|----------------------------------|--------------------------------------------|
| `git branch`                     | List all local branches.                   |
| `git branch <branch-name>`       | Create a new branch.                       |
| `git checkout <branch-name>`     | Switch to an existing branch.              |
| `git checkout -b <branch-name>`  | Create and switch to a new branch.         |
| `git branch -d <branch-name>`    | Delete a local branch.                     |
| `git branch -D <branch-name>`    | Force delete a branch with unmerged changes. |
| `git branch -r`                  | List all remote branches.                  |
| `git branch -a`                  | List all local and remote branches.        |

---

## 🔗 Merging & Rebasing

| Command                           | Purpose                                               |
|-----------------------------------|--------------------------------------------------------|
| `git merge <branch-name>`         | Merge specified branch into current branch.            |
| `git rebase <branch-name>`        | Reapply commits of current branch on top of another.   |
| `git rebase --abort`              | Abort ongoing rebase.                                  |
| `git rebase --continue`           | Continue rebase after resolving conflicts.             |

---

## 🚫 Undoing Changes

| Command                                 | Purpose                                                  |
|-----------------------------------------|-----------------------------------------------------------|
| `git reset --soft HEAD~1`               | Unstage last commit but keep changes in working directory. |
| `git reset --mixed HEAD~1` *(default)*  | Unstage and reset index but keep working directory.        |
| `git reset --hard HEAD`                 | Discard all local changes and reset to last commit.        |
| `git checkout -- <file>`                | Restore a specific file to its last committed state.       |
| `git revert <commit-hash>`              | Create a new commit that undoes changes from a previous commit. |
| `git reflog`                            | View history of Git actions (useful to recover lost commits). |

---

## 💡 Stashing Changes

| Command                    | Purpose                                      |
|----------------------------|----------------------------------------------|
| `git stash`                | Temporarily save modified files (not committed). |
| `git stash pop`            | Apply stashed changes and remove them.       |
| `git stash list`           | List all saved stashes.                      |
| `git stash apply`          | Apply most recent stashed changes.           |

---

## 🔍 Inspecting History

| Command                        | Purpose                                           |
|--------------------------------|---------------------------------------------------|
| `git log`                      | View commit history.                              |
| `git log --oneline`            | Condensed view of commit history.                 |
| `git blame <file>`             | See who made what changes in a file line-by-line. |
| `git show <commit-hash>`       | Display details of a specific commit.             |
| `git diff`                     | Show differences between working directory and index. |
| `git diff --staged`            | Show differences between staged changes and last commit. |

---

## 🏷️ Tagging

| Command                              | Purpose                               |
|--------------------------------------|---------------------------------------|
| `git tag v1.0`                       | Create a lightweight tag.             |
| `git tag -a v1.0 -m "Release 1.0"`   | Create an annotated tag with message. |
| `git push origin v1.0`               | Push a tag to remote repository.      |

---

## 🛑 Resolving Merge Conflicts

When merging branches, Git may flag conflicts:

### Conflict Markers:
```plaintext
<<<<<<< HEAD
Your changes
=======
Their changes
>>>>>>> their-branch
```

**Steps to Resolve:**
1. Open conflicting files.
2. Remove markers and choose which changes to keep.
3. Save the file.
4. Stage the resolved file:

```bash
git add <file>
```
5. Complete the merge:

```bash
git commit -m "Resolved merge conflicts"
```

🧹 Ignoring Files
Create a .gitignore file to prevent tracking unwanted files.

---
| Command                              | Purpose                               |
|--------------------------------------|---------------------------------------|
| `echo "<pattern>" >> .gitignore`     | Add pattern to ignore files/folders.  |
| `git tag -a v1.0 -m "Release 1.0"`   | Remove file from Git without deleting.|

---

```bash
echo "*.log" >> .gitignore
echo "/build/" >> .gitignore
```

🔄 Remote Repository Operations

---

| Command                        | Purpose                                           |
|--------------------------------|---------------------------------------------------|
| `git remote -v`                | Show configured remote repositories.              |
| `git remote add origin <url>`  | Add a remote repository.                          |
| `git fetch`                    | Download objects and refs from remote.            |
| `git fetch <remote>`           | Fetch from a specific remote.                     |
| `git push origin <branch>`     | Push changes to a specific remote branch.         |

---

✅ Summary Tips
* Always run `git status` before committing or pushing.
* Use `git diff` or `git diff --staged` to review changes.
* Avoid force pushes unless necessary (`git push --force`).
* Keep your feature branches small and focused.
* Resolve conflicts early during merges or rebases.

<mark>⚠️ Tip: When in doubt, use `git reflog` to find past operations and restore lost work. </mark>

Wish you a very Happy coding! 🚀 - Sumit K Shukla

# Git



## Git Quick Reference Sheet

A practical cheat sheet for everyday Git operations.

### 1. Configuration and initialization

| Command                                            | Description                         |
| -------------------------------------------------- | ----------------------------------- |
| `git --version`                                    | Check installed Git version         |
| `git config --global user.name "Your Name"`        | Set author name                     |
| `git config --global user.email "you@example.com"` | Set author email                    |
| `git init`                                         | Initialize a local repository       |
| `git clone <url>`                                  | Clone a remote repository           |
| `git remote -v`                                    | Show configured remote repositories |

### 2. Check repository status

| Command                           | Description                                |
| --------------------------------- | ------------------------------------------ |
| `git status`                      | Show modified, staged, and untracked files |
| `git status -sb`                  | Show short status and current branch       |
| `git diff`                        | Show unstaged changes                      |
| `git diff --staged`               | Show staged changes                        |
| `git diff --check`                | Check changes for whitespace errors        |
| `git log --oneline -10`           | Show last 10 commits                       |
| `git log --oneline --graph --all` | Visualize commit history                   |

### 3. Stage and commit changes

| Command                        | Description                               |
| ------------------------------ | ----------------------------------------- |
| `git add file.md`              | Stage a specific file                     |
| `git add .`                    | Stage all changes under current directory |
| `git add -p`                   | Interactively stage selected changes      |
| `git restore --staged file.md` | Unstage a file, preserving edits          |
| `git commit -m "message"`      | Commit staged changes                     |
| `git show HEAD`                | Display the latest commit                 |
| `git show --stat HEAD`         | Show files changed in latest commit       |

### 4. Branch operations

| Command                 | Description                         |
| ----------------------- | ----------------------------------- |
| `git branch`            | List local branches                 |
| `git branch -a`         | List local and remote branches      |
| `git switch main`       | Switch to the `main` branch         |
| `git switch -c feature` | Create and switch to a new branch   |
| `git merge feature`     | Merge `feature` into current branch |
| `git branch -d feature` | Delete a merged local branch        |

### 5. Working with GitHub

| Command                      | Description                                           |
| ---------------------------- | ----------------------------------------------------- |
| `git remote -v`              | Inspect remote URLs                                   |
| `git fetch origin`           | Download remote updates without merging               |
| `git pull --ff-only`         | Update current branch without creating a merge commit |
| `git push origin main`       | Push local `main` to GitHub                           |
| `git push -u origin feature` | Publish a new branch and set its upstream             |
| `git branch -vv`             | Show branch tracking information                      |

### 6. Undo and restore

| Command                               | Description                                          |
| ------------------------------------- | ---------------------------------------------------- |
| `git restore file.md`                 | Discard unstaged changes in a file                   |
| `git restore --staged file.md`        | Unstage without discarding file edits                |
| `git restore --source=HEAD~1 file.md` | Restore a file from the previous commit              |
| `git revert <commit>`                 | Create a new commit that reverses an earlier commit  |
| `git stash push -m "WIP"`             | Temporarily save tracked changes                     |
| `git stash list`                      | List saved stashes                                   |
| `git stash pop`                       | Reapply the latest stash and remove it if successful |

**Caution:** `git restore file.md` discards local unstaged edits. For published history, prefer `git revert` over rewriting commits. Avoid `git reset --hard` and force-pushing unless you fully understand the consequences.

### 7. Tags and releases

| Command                              | Description           |
| ------------------------------------ | --------------------- |
| `git tag`                            | List tags             |
| `git tag -a v1.0.0 -m "Release 1.0"` | Create annotated tag  |
| `git push origin v1.0.0`             | Push a specific tag   |
| `git show v1.0.0`                    | Inspect tagged commit |

### 8. Common daily workflow

For an existing project such as ShengWiki:

1. Check changes: `git status`
2. Inspect edits: `git diff`
3. Stage files: `git add .`
4. Review staged changes: `git diff --staged`
5. Validate whitespace: `git diff --check`
6. Commit: `git commit -m "docs: update wiki"`
7. Push: `git push origin main`

**Remember:** Stage → Review → Commit → Push.

For ShengWiki, commits and pushes require your explicit approval. Run the final two commands only after confirming which files should be published.

---

### Useful concepts

| Term                 | Meaning                                            |
| -------------------- | -------------------------------------------------- |
| Working tree         | Files currently in your project directory          |
| Staging area / Index | Changes selected for the next commit               |
| Commit               | Saved snapshot of the repository                   |
| Branch               | Movable pointer to a line of commits               |
| HEAD                 | Reference to the currently checked-out commit      |
| Origin               | Conventional name of a remote repository           |
| Fetch                | Download remote information without integrating it |
| Pull                 | Fetch and integrate changes                        |
| Push                 | Send local commits to a remote repository          |
| `.gitignore`         | Rules excluding untracked files from Git           |

**Official documentation:** https://git-scm.com/docs

[**Learn Git Branching**](https://learngitbranching.js.org/?locale=zh_CN)

## 经验和原则

- 早用分支
- 改变文件夹结构前后一定要commit

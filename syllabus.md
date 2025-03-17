# Compact Git Reversal Toolkit

### Core Commands

```bash
git fetch origin
git pull origin <branch>
git reset --hard <commit>
git merge --abort
git restore <file>
git restore --staged <file>
git reflog
git push --force
git status
git log --oneline --graph
```

## Reversal Scenarios

- **Undo pull (No Conflict):**  
  ```bash
  git reset --hard HEAD^
  ```
- **Undo pull (Conflict):**  
  ```bash
  git merge --abort
  ```
- **Undo Edits (Uncommitted):**  
  ```bash
  git restore <file>
  ```
- **Undo `git add`:**  
  ```bash
  git restore --staged <file>
  ```
- **Full Reset to Remote:**  
  ```bash
  git fetch origin; git reset --hard origin/main
  ```
- **Recover Lost Commit:**  
  ```bash
  git reflog; git reset --hard <sha>
  ```

## Edge Cases

- **Force-Pushed Remote:**  
  ```bash
  git fetch; git reset --hard origin/main
  ```
- **Conflict Resolved & Committed:**  
  ```bash
  git reset --hard <sha^>
  ```
- **Dirty Working Tree:**  
  ```bash
  git stash; [undo]; git stash pop
  ```

## Key Concepts

- **Working Tree:** Uncommitted file changes  
- **Index:** Staged changes (`git add`)  
- **HEAD:** Current commit/branch pointer  
- **`refs/heads/`**: Local branches  
- **`refs/remotes/`**: Remote-tracking branches  
- **Merge Conflict:** Markers in files  
- **Reflog:** 30-day history of HEAD moves  


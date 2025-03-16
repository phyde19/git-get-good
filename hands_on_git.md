# Git Hands-On Practice List

## Core Skills
- Create feature branches: `git checkout -b feature/xyz`
- Merge vs Rebase:
  - Try both on sample branches
  - `git merge feature/xyz`
  - `git rebase main`

## Conflict Resolution
- Create deliberate conflicts
- Resolve with mergetool: `git mergetool`
- Abort merges: `git merge --abort`

## History Management
- Squash commits: `git rebase -i HEAD~3`
- Cherry-pick: `git cherry-pick <commit-hash>`
- Undo commits: `git reset --soft HEAD~1`

## Team Workflows
- Pull with rebase: `git pull --rebase origin main`
- Force push safely: `git push --force-with-lease`
- Check branch status: `git branch -vv`

## Transparency Tools
- View history: `git log --graph --oneline --all`
- See who changed what: `git blame file.txt`
- Investigate history: `git reflog`

## Emergency Recovery
- Find lost commits: `git reflog`
- Undo rebase: `git reset --hard ORIG_HEAD`
- Fix detached HEAD: `git checkout -b recovery-branch`
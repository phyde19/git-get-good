# Git Notes

### Config
```bash
git config --list # view configs
```

### Making Changes
```bash
#init with branch name
git init -b main

# add changes from working dir to staging
git add personal_notes.md
git add .  # <- add current directory

# commit staging changes to git directory
git commit -m "init commit"

git push origin main
git push -u origin main # set tracking so git push/pull defaults
```

### Transparency
```bash
git log                    # view commits
git log --graph --oneline  # graph with compact view

git branch                 # view branches
```

### Branches
```bash
git branch -d my-branch
```

### undo things
```bash
git reset HEAD
git reset --soft HEAD~1
git reset --hard HEAD   # remove everything
```

### Remotes 
```bash
git clone https://github.com/phyde19/git-get-good.git  # sets origin

# view remotes
git remote -v 
# add remote
git remote add github https://github.com/phyde19/git-get-good.git

# make changes 
git push -u origin main         # push branch
git push origin --delete main   # delete branch
```

## Misc
What is a bare repository? This is just a .git database without actual working files. This is the basis for what you get in a hosted repository platform like GitHub or Azure DevOps. 

### Git reset modes
Each mode controls how much Git "undoes":
--soft = Undo commit but keep staged.
--mixed = Undo commit & unstage.
--hard = Undo everything (commit, staging, and working dir).
Breaking it Down Visually
Imagine you just committed some changes and now you reset:

| Command | HEAD Moves? | Staging Area Reset? | Working Dir Reset? | What You See After? |
|---------|------------|---------------------|---------------------|---------------------|
| `git reset --soft HEAD~1` | ✅ Yes | ❌ No | ❌ No | Commit undone, but files stay staged |
| `git reset HEAD~1` *(default `--mixed`)* | ✅ Yes | ✅ Yes | ❌ No | Commit undone, files unstaged but unchanged |
| `git reset --hard HEAD~1` | ✅ Yes | ✅ Yes | ✅ Yes | Commit undone, files wiped out |


## 🔹 Why Use --soft?
This is useful when you just want to rewrite the last commit without touching your files.

🛠 Common Use Case: Rewriting the Last Commit
You made a commit, but you realize you need to change the message or add a file:

```bash
git reset --soft HEAD~1  # Undo last commit, keep changes staged
git commit -m "New commit message"
🚀 This is basically a manual version of git commit --amend.
```

# How git stores commits? 
Short answer, git will save updated files in full and only reference 
old unchanges files from previous commits. Apparently it does not save diffs
as I previous thought.


# Common Errors
"detached HEAD" - occurs when HEAD is pointing directly to a commit instead of branch



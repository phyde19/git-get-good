# Git Notes

### Init
```bash
#init with branch name
git init -b main

# add changes from working dir to staging
git add personal_notes.md
git add .  # <- add current directory

# commit staging changes to git directory
git commit -m "init commit"
```


# How git stores commits? 
Short answer, git will save updated files in full and only reference 
old unchanges files from previous commits. Apparently it does not save diffs
as I previous thought.
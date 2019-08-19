# Handy Tricks for Git

View current changes
``` bash
git status
```

Undo changes on a particular file, aka rollback to previous commit.
```bash
git checkout -- <path/to/file.ext>
```

Blow away all current changes
```bash
git reset --hard
```

## Branches
See local branchs
```bash
git branch
```

List all branchs
```bash
git branch -a
```

Switch branch or create a new branch
```bash
git checkout <branchname>
```
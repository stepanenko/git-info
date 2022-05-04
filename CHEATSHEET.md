
## Git Cheatsheet

`git reset --hard` - undo last commit

> The above throws away all your uncommitted changes. Always check that the output of git status is clean (that is, empty) before using it.

---

`git log --oneline` - logs all commits, one per line (use `down` key to scroll or hit `q` to exit)

`git checkout -` - switch to the previous branch

`git commit -am "my changes"` - git add + git commit

`git commit --amend -m` - edit the latest commit

`git commit --amend --no-edit` - edit the latest commit (e.g. add files to it) keeping the same commit message

- `--amend` - works on the commits not yet pushed to the remote repo

`git revert <commit>` - revert the changes and create a new commit with the reverted changes

- `<commit>` - commits you want to revert

---

`git config --global -l` - show global config

`git config --local -l` - show local config
  

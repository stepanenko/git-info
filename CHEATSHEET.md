
## Git Cheatsheet

`git log --oneline` - logs all commits, one per line (use `down` key to scroll or hit `q` to exit)

`git checkout -` - switch to the previous branch

`git commit -am "my changes"` - git add + git commit

`git commit --amend -m` - edit the latest commit

`git commit --amend --no-edit` - edit the latest commit (e.g. add files to it) keeping the same commit message

- `--amend` - works on the commits not yet pushed to the remote repo

`git revert <commit>` - revert the changes and create a new commit with the reverted changes

- `<commit>` - commits you want to revert

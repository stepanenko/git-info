
# git

## 1. Revert a commit that has already been pushed to remote

`git revert -m 1 <commit-hash>`  
`git revert` - commits your changes

`-m 1` indicates that you'd like to revert to the tree of the first parent before the merge  
`<commit-hash>` is the commit hash of the merge that you would like to revert.

## 2. Cherry-picking a commit

Make sure you are on the branch you want to apply the commit to: `git switch master`

`git cherry-pick <commit-hash>`

## 3. Update master branch while being on another branch

As long as you're doing a **fast-forward** merge simply use `git fetch <remote> <sourceBranch>:<destinationBranch>`.

- Example 1:

`git fetch origin master:master` - merge remote branch origin/master into local branch master, without having to checkout master first

Then, if you want, you can run `git merge master` - to merge master into the branch you are currently on

- Example 2:

`git fetch . foo:master` - merge local branch foo into local branch master, without having to checkout master first

Here `.` means to use the local repository as the "remote"

---

## 4. Rebase flow

Being on <my_fix> branch run: `git rebase master` - rebasing <my_fix> with the latest local master branch

[Rebase vs Merge](https://github.com/stepanenko/git-info/blob/master/Rebase_vs_Merge.md)

---

## 5. Pulling a specific branch from git

**Option 1:**

- Step 1: `git fetch origin my-branch`
- Step 2: `git checkout my-branch` - you are on your `my-branch` branch

**Option 2:**

> If you did a clone, then all branches should be available to you. You need to checkout the branch: `git checkout my-branch`

- Step 1: If the branch isn't available for whatever reason, then you can create it: `git checkout -b my-branch`  
`-b` specifies "create branch"
- Step 2: Then fetch and merge this branch into your just created local one: `git pull origin my-branch`

---

## 6. Rename branch

**Option 1:**

- Step 1: `git checkout old-name`
- Step 2: `git branch -m new-name`

**Option 2:**

> Let's say you are on the `master` branch
- Step 1: `git branch -m old-name new-name`

---

## 7. Stop tracking specific files locally
```
git update-index --assume-unchanged common/default/settings.json
```
Where `common/default/settings.json` is some file that you want to stop tracking

---

## 8. First-time login guide

https://kbroman.org/github_tutorial/pages/first_time.html

---

## 9. Happened Errors

### After running `git clone link` the following occurs (on Mac M1):

```
git-lfs filter-process: git-lfs: command not found
fatal: the remote end hung up unexpectedly
warning: Clone succeeded, but checkout failed
```
Solution: Install **Git LFS** extension

**Option 1:**

- Download **Git LFS** extension from https://git-lfs.github.com/
- Installed by running `./install.sh` inside the unpacked folder
- Set up **Git LFS** for your user account by running `git lfs install`

**Option 2:**

```
brew install git-lfs
git lfs install
```

---

### Warning while pulling from some branch, e.g. `git pull origin <branch_name>`

> Pulling without specifying how to reconcile divergent branches is
discouraged. You can squelch (silence) this message by running one of the following
commands sometime before your next pull:
 
- `git config pull.rebase false`  - merge (the default strategy)
- `git config pull.rebase true`   - rebase
- `git config pull.ff only`       - fast-forward only

> You can replace "git config" with "git config --global" to set a default
preference for all repositories. You can also pass --rebase, --no-rebase,
or --ff-only on the command line to override the configured default per invocation, e.g:

`git pull <branch_name> --ff-only`

Watch out as after that you may get `fatal: Not possible to fast-forward, aborting.`

---

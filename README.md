
## GIT Notes

### 1. Update master branch while being on another branch

As long as you're doing a **fast-forward** merge simply use `git fetch <remote> <sourceBranch>:<destinationBranch>`.

Example 1:

`git fetch origin master:master` - merge remote branch origin/master into local branch master, without having to checkout master first

Then, if you want run `git merge master` - to merge master into the branch you are currently on

Example 2:

`git fetch . foo:master` - merge local branch foo into local branch master, without having to checkout master first

Here `.` means to use the local repository as the "remote"

---

### 2. Pulling a specific branch from GIT:

**Option 1:**

If you did a clone, then all branches should be available to you. You need to checkout the branch:
```
git checkout my-branch
```
Step 1: If the branch isn't available for whatever reason, then you can create it and then pull it:
```
git checkout -b my-branch
```
`-b` specifies "create branch"

Step 2: Fetch and merge this branch into your local one:
```
git pull origin my-branch
```
**Option 2:**

Step 1: `git fetch my-branch`

Step 2: `git checkout my-branch`

You are on your my-branch branch.

---

### 3. Stop tracking specific file locally:
```
git update-index --assume-unchanged common/default/settings.json
```
Where `common/default/settings.json` is some file that you want to stop tracking

---

### 4. Happened Errors

- After running `git clone link` the following occurs (on Mac M1) :
```
git-lfs filter-process: git-lfs: command not found
fatal: the remote end hung up unexpectedly
warning: Clone succeeded, but checkout failed
```
Solution: Install **Git LFS** extension

Option 1:  
- Download **Git LFS** extension from https://git-lfs.github.com/
- Installed by running `./install.sh` inside the unpacked folder
- Set up **Git LFS** for your user account by running `git lfs install`

Option 2:
```
brew install git-lfs
git lfs install
```

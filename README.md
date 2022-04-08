
## GIT Notes


### 1. Pulling a specific branch from GIT:

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

### 2. Stop tracking specific file locally:
```
git update-index --assume-unchanged common/default/settings.json
```
Where `common/default/settings.json` is some file that you want to stop tracking

---

### 3. Happened Errors

After running `git clone link` the following occurs (on Mac M1) :
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

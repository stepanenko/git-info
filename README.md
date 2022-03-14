
## GIT Notes

Created: 3.02.2022

---

### Pulling a specific branch from GIT:

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

### Stop tracking a file on certain working copies:
```
git update-index --assume-unchanged common/default/settings.json
```


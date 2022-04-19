
### Short Version

- Merge takes all the changes in one branch and merges them into another branch in one commit.

- Rebase says I want the point at which I branched to move to a new starting point

### So when do you use either one?

- Merge

Let's say you have created a branch for the purpose of developing a single feature. When you want to bring those changes back to master, you probably want merge (you don't care about maintaining all of the interim commits).

- Rebase

A second scenario would be if you started doing some development and then another developer made an unrelated change. You probably want to pull and then rebase to base your changes from the current version from the repository.

--- 

- Merge - a commit, that combines all changes of a different branch into the current.

- Rebase - re-comitting all commits of the current branch onto a different base commit.

### What are the main differences between merge and rebase?

- `merge` executes only one new commit, `rebase` typically executes multiple (number of commits in current branch).
- `merge` produces a new generated commit (the so called merge-commit), `rebase` only moves existing commits.

### In which situations should we use a merge?

- Use `merge` whenever you want to add changes of a branched out branch back into the base branch.

Typically, you do this by clicking the "Merge" button on Pull/Merge Requests, e.g. on GitHub.

### In which situations should we use a rebase?

- Use `rebase` whenever you want to add changes of a base branch back to a branched out branch.

Typically, you do this in feature branches whenever there's a change in the main branch.

### Why not use merge to merge changes from the base branch into a feature branch?

- The git history will include many unnecessary merge commits. If multiple merges were needed in a feature branch, then the feature branch might even hold more merge commits than actual commits!

- This creates a loop which destroys the mental model that Git was designed by which causes troubles in any visualization of the Git history.

Imagine there's a river. Water is flowing in one direction (direction of time in Git history). Now and then, imagine there's a branch to that river and suppose most of those branches merge back into the river. That's what the flow of a river might look like naturally. It makes sense.

But then imagine there's a small branch of that river. Then, for some reason, the river merges into the branch and the branch continues from there. The river has now technically disappeared, it's now in the branch. But then, somehow magically, that branch is merged back into the river. Which river you ask? I don't know. The river should actually be in the branch now, but somehow it still continues to exist and I can merge the branch back into the river. So, the river is in the river. Kind of doesn't make sense.

This is exactly what happens when you merge the base branch into a feature branch and then when the feature branch is done, you merge that back into the base branch again. The mental model is broken. And because of that, you end up with a branch visualization that's not very helpful.

### Downsides of rebase:

- Because a rebase moves commits (technically re-executes them), the commit date of all moved commits will be the time of the rebase and the git history loses the initial commit time. So, if the exact date of a commit is needed for some reason, then merge is the better option. But typically, a clean git history is much more useful than exact commit dates.
- If the rebased branch has multiple commits that change the same line and that line was also changed in the base branch, you might need to solve merge conflicts for that same line multiple times, which you never need to do when merging. So, on average, there's more merge conflicts to solve.

### Tips to reduce merge conflicts when using rebase:

- Rebase often. I typically recommend doing it at least once a day.
- Try to squash changes on the same line into one commit as much as possible.

---

Source: https://stackoverflow.com/questions/804115/when-do-you-use-git-rebase-instead-of-git-merge

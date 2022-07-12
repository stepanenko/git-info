
# Stash Commands

Side Note: In English "stash" synonyms are: _store, cache, pack, hide, conceal, save, keep_...

`git stash list` - list all stashed items

`git stash apply` - apply the latest stash item

`git stash apply N` - to apply specific stash item (using `N` - index of stash, only works since version 2.11)

`git stash push -m "My work"` - add stash item with a comment

`git stash clear` - delete all stashed items

`git stash drop N` - delete specific stash item (using `N` - index of stash, only works since version 2.11)

`git stash drop stash@{index}` - delete specific stash item (`...drop "stash@{index}"` on Windows)

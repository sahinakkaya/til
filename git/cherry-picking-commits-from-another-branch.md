You have a commit which contains a good code change but it is in another branch?

```bash
# pick the commit 
git cherry-pick <sha>

# apply changes introduced by commit but do not commit the changes
git cherry-pick <sha> -n
git cherry-pick <sha> --no-commit

# pick all the commits from A to B (A is older than B, remove caret (^) if you don't want to include A)
git cherry-pick "A^..B"
```

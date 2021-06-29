Let's say you are in `wip` branch and you didn't push your changes to server yet. If you want to get all the changes from master:

```
git checkout master
git pull
git checkout wip
git rebase master
```

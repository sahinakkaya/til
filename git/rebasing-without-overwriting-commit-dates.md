When you do 

```
git rebase -i commitish
```
and edit some commits, you will recreate the history hence all the commits coming after edited one will have the same date and time. If you don't want this behaviour here is the trick:
```
git rebase --committer-date-is-author-date -i commitish
```
Note that you need git version 23.19 or greater to do this in interactive mode.

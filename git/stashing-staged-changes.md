As of Git 2.35 you can stash only staged changes with `--staged` option. 

```
$ git add foo
$ git stash push --staged
$ # You can also add a message with `-m`
$ git stash push --staged -m "message"

```

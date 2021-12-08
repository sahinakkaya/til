You can add filename to `git log` to view all the commit history of a file:

```bash
git log my_file
```

If you want to view diff's, add `-p` option:
```bash
git log -p my_file
```

If you want to continue listing the file history beyond renames, add `--follow` option:
```bash
git log --follow -p my_file
```



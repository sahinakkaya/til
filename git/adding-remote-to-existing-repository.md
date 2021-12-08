If you have an existing repository and want to add a new remote you can use this command:
```bash
git remote add <name> <url>
```
Example:
```bash
git remote add origin git@github.com:Asocia/til.git
git push -u origin my_branch
```

If you get an error like
```
error: remote origin already exists.
```

you can:
  
    - remove the origin and try again. `git remote remove origin`
    - add it with a different name. `git remote add ... ...`

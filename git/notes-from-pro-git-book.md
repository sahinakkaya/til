I'm reading Pro Git book and I learn some cool stuff. I don't know if I'm going to use these, so I'm not sure if it's a good idea to make seperate files for all the commands. But they are just so cool that I want to note it somewhere. So this file is created specifically for this purpose. If I ever need a command from this file, I will move it to their own file.

- Limiting the logs since/until some time, or from specific author

If you to know which changes are made since some time, use `--since` option like:

```
git log --since=2.weeks
```
or until some time
```
git log --until="20-01-2020"
```

These commands works with lots of formats, you can specify a specific date like "2008-01-15", or a relative date such as "2 years 1 day 3 minutes ago"

The --author option allows you to filter on a specific author
```
git log --author="Asocia"
```

- Getting the logs for a specific string 


Another really helpful filter is the -S option (colloquially referred to as Git’s “pickaxe” option), which takes a string and shows only those commits that changed the number of occurrences of that string. For instance, if you wanted to find the last commit that added or removed a reference to a specific function, you could call:
```
git log -S function_name
```


- Adding remotes and fetching them


We’ve mentioned and given some demonstrations of how the git clone command implicitly adds the origin remote for you. Here’s how to add a new remote explicitly. To add a new remote Git repository as a shortname you can reference easily, run git remote add <shortname> <url>:

```
$ git remote -v
$ git remote add pb https://github.com/paulboone/ticgit
$ git remote -v
$ git fetch pb
```
Paul’s master branch is now accessible locally as pb/master — you can merge it into one of your branches, or you can check out a local branch at that point if you want to inspect it.

- Using git switch to create and checkout branches

From Git version 2.23 onwards you can use `git switch` instead of `git checkout` to:
    - Switch to an existing branch: `git switch testing-branch`.
    - Create a new branch and switch to it: `git switch -c new-branch`. The `-c` flag stands for create, you can also use the full flag: `--create`.  
    - Return to your previously checked out branch: `git switch -`.


- Renaming branches

Suppose you have a branch that is called `bad-branch-name` and you want to change it to `corrected-branch-name`, while keeping all history. You also want to change the branch name on the remote (GitHub, GitLab, other server). How do you do this? Rename the branch locally with the `git branch --move` command:
```
git branch --move bad-branch-name corrected-branch-name
```

This replaces your `bad-branch-name` with `corrected-branch-name`, but this change is only local for now. To let others see the corrected branch on the remote, push it:

```
git push --set-upstream origin corrected-branch-name
```
To delete the old branch name:
```
git push origin --delete bad-branch-name
```

- Pushing a local branch into a remote branch that is named differently

```
# our branch is serverfix and we don't want to push it with this name
git push origin serverfix:awesomebranch
```

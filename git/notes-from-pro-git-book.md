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

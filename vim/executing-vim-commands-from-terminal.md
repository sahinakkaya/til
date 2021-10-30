You can execute vim commands in terminal by prefixing your command with `+` symbol:

```
vim filename +/searchterm
vim +PlugInstall
vim filename +g/foo/d
vim filename "+g/foo/norm dap"
```

These commands will open vim and perform your command. And if you want to immediately save and exit (useful for shell scripts):
```
ex "+g/test/norm dap" "+wq" filename
```



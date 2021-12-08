You can execute vim commands in terminal by prefixing your commands with `+` symbol:

```bash
vim filename +/searchterm
vim +PlugInstall
vim filename +g/foo/d
vim filename "+g/foo/norm dap"
vim filename "+g/test/norm dap" +wq
```




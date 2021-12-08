You can clone a repository with ssh and pull/push without having to enter your credentials. If you already cloned it with https and want to change your remote url, do this:
```bash
❯ git remote -v
origin  https://github.com/Asocia/dotfiles.git (fetch)
origin  https://github.com/Asocia/dotfiles.git (push)
❯ git remote set-url origin git@github.com:Asocia/dotfiles.git
```

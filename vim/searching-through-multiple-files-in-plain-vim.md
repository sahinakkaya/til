You can search through multiple files using `vimgrep` command.

```vim
# search for string all python files in the current dir
:vimgrep string *.py
# search for string all python files in the current dir and subdir of the current dir
:vimgrep string  **/*.py


Here are the commands you can use to navigate through search matches:
  - `:cn` - jump to the next match.
  - `:cN` - jump to the previous match.
  - `:clist` - view all the files that contain the matched string
  - `:cc number` - jump to specific match number, which you get from :clist output.
```

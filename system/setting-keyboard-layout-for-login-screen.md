Recently, I switched to dvorak layout and I am using it everywhere to get used to it. This was the command that worked everywhere (including the login screen):

```bash
localectl --no-convert set-x11-keymap us pc105 dvp caps:ctrl_modifier
```

I don't know what `--no-convert` does but I saw it on the Arch Wiki :D

Here are some helpful links:

  - `https://wiki.archlinux.org/title/Xorg/Keyboard_configuration`
  - `https://unix.stackexchange.com/a/111042/417514`

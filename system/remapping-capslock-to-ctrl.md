Story: I know I'm suffering this from so much. Everytime I install a new system, I'm fooled by the application I'm using whenever I try to do something with 'Ctrl'. My left Ctrl is broken so I remapped my Caps Lock to Ctrl. It was one of the best things I have done ever! I would remap it even if I have a fully functioning Ctrl key now.

Here is how it should be done:

If you want to remap it for X server, add the following line to your `~/.xsession` or `~/.xinitrc`. Make sure to add it before `exec whatever_window_manager` you are using:

```
setxkbmap -option 'caps:ctrl_modifier'
```
[source](https://superuser.com/questions/566871/how-to-map-the-caps-lock-key-to-escape-key-in-arch-linux)

And for console:
 - tried the following but it didn't work. Needs investigating.
[Arch Wiki](https://wiki.archlinux.org/title/Linux_console/Keyboard_configuration#Creating_a_custom_keymap)
[SO](https://stackoverflow.com/questions/28651864/change-capslock-to-ctrl-archlinux-command-line)


When you install a new system, touchpad may not work as you expect. The scrolling direction is probably reversed and tap to click is not enabled. You can fix it by creating a file `/etc/X11/xorg.conf.d/30-touchpad.conf` and put the following content inside it:
```
Section "InputClass"
    Identifier "touchpad catchall"
    Driver "libinput"
    Option "Tapping" "on"
    Option "NaturalScrolling" "true"
EndSection
```

After that you need to restart X server.

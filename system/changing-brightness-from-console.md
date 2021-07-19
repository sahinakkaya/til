Story: Today is my first day with Arch. Whatever problem I'm facing is clearly documented in Arch Wiki. I'm falling in love with the system. It's just another level. I feel like I don't even need to create TIL files anymore as everything is just couple of keystrokes away. I'll see how it goes.

Read [this](https://wiki.archlinux.org/title/backlight) and you are done :D

Here is the tl;dr part.

Run `ls /sys/class/backlight/` to see which graphics card is managing your backlight. I'm assuming you get an ouput like `intel_backlight`. Then run this:
```
ls /sys/class/backlight/intel_backlight
actual_brightness bl_power brightness device/
max_brightness power/ scale subsystem/ type uevent
```
Read the `max_brightness` value and then set your brightness to something smaller than that value:
```
cat /sys/class/backlight/intel_backlight/max_brightness
echo 100 > /sys/class/backlight/intel_backlight/brightness
```
Note: You should be `root` to execute the previous command. If you want to modify it without root priveleges:
```
/etc/udev/rules.d/backlight.rules

RUN+="/bin/chgrp video /sys/class/backlight/intel_backlight/brightness"
RUN+="/bin/chmod g+w /sys/class/backlight/intel_backlight/brightness"
```
and add yourself to the `video` group. 
```
sudo usermod -aG video $USER
```

Now you can use [`light`](https://github.com/haikarainen/light).

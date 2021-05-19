TL;DWrote. 

Check out [this](https://cravencode.com/post/essentials/enable-tap-to-click-in-i3wm/) site. In case the site becomes unavailable in the future, here is the essential part:

## Enable tap to click in i3 WM
When switching from Gnome or KDE to using i3 tiling window manager on a laptop, you might be frustrated to discover that tap-to-click on your touchpad no longer functions. This is how to re-enable tap-to-click in i3 by properly using X11 configuration.

## The wrong way
Many posts I found when trying to solve this for myself referred users to:

- Run xinput list
- Reading through the list for what you think is your touchpad
- Using the id= value from the prior step to run xinput list-props <device>
- Looking for the ID value for “Tapping Enabled” listed between a set of parenthesis
- Adding an exec to your i3 config to run xinput set-prop <device> <property> 1

While this is effective it certainly isn’t copy-paste drop dead simple and is a work around solution, rather than solving the issue using the capabilities X11 provides.

## Doing it the X11 config way
X11 provides configurations in a directory “X11/xorg.conf.d/” this directory could live in various places on your system depending on your distribution. However, X11 will always attempt to also load configurations from /etc/X11/xorg.conf.d/ when present. To ensure the directory exists, run:
```
sudo mkdir -p /etc/X11/xorg.conf.d
```
Next we’ll create a new file “90-touchpad.conf”. The configuration file names end with .conf and are read in ASCII order—by convention file names begin with two digits followed by a dash.
```
sudo touch /etc/X11/xorg.conf.d/90-touchpad.conf
```
Now open up the file your editor of choice (with suitable write permission of course) and paste the following:
```
Section "InputClass"
        Identifier "touchpad"
        MatchIsTouchpad "on"
        Driver "libinput"
        Option "Tapping" "on"
EndSection
```
## Additional libinput options
Libinput support additional options beyond tapping, you can add and configure each one by adding them on new lines after Option "Tapping" "on" in your /etc/X11/xorg.conf.d/90-touchpad.conf, for example:
```
Section "InputClass"
        Identifier "touchpad"
        MatchIsTouchpad "on"
        Driver "libinput"
        Option "Tapping" "on"
        Option "TappingButtonMap" "lrm"
        Option "NaturalScrolling" "on"
        Option "ScrollMethod" "twofinger"
EndSection
```

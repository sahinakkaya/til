Today an annoying border showed up around my tmux pane and I didn't know what it is or why it is showing up. I killed the pane and moved on. After some time, it showed up again but this time I know how did I get it. I accidentally pressed `prefix m`. After searching the shortcut on the internet, I found that this keybinding is `m`arking the pane. 

> -m and -M are used to set and clear the marked pane. There is one marked pane at a time, setting a new marked pane clears the last. The marked pane is the default target for -s to join-pane, swap-pane and swap-window.

To move a pane from one window to another, `prefix m` to mark the pane and move to other window then `:join-pane`.

When my Ctrl key broken, I remapped Capslock to Ctrl as it was the most useless key on the keyboard. Its position was great and suddenly all the shortcuts involving Ctrl become much more easier. Then I forget about Capslock and map it to Ctrl even if both keys are functioning. Recently I made some custom keyboards for myself and I thought maybe I can bring back Capslock. Currently, my right shift key acts as Capslock if tapped once or Shift if being hold. This is great

I am a vim user and I don't use Capslock other than typing some constant variable names or SQL syntax etc. They are all happening in vim, specifically, in insert mode. Whenever I switch to normal mode, I want my Capslock to be off. I sometimes forget and instead of moving down with `j`, I find myself `J`oining lines. This happened more than 3 times so it is time to do something. 

I could solve this problem in keyboard level because I have a programmable keyboard. I didn't want to this because sometimes I use my laptop's keyboard and I don't want them to behave differently. So I solved it on OS level. Here are the commands that I run in order to achieve this effect:
```bash
mkdir -p ~/.xkb/keymap/
mkdir -p ~/.xkb/symbols/
vim ~/.xkb/symbols/mysymbols

partial modifier_keys
xkb_symbols "esc_breaks_caps" {
    key <ESC> {
        type = "ALPHABETIC",
        actions [Group1] = [
            SetMods(modifiers=none),
            SetMods(modifiers=Lock,clearLocks)
        ]
    };
};

setxkbmap -print > ~/.xkb/keymap/mykbd
vim ~/.xkb/keymap/mykbd
# and add +mysymbols(esc_breaks_caps) to xkb_symbols

xkbcomp -I$HOME/.xkb ~/.xkb/keymap/mykbd $DISPLAY
```

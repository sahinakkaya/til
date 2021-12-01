## Story
Since I started touch typing, I hated how all the keys are placed in awkward positions and gave my wrists pain. I decided to switch to a better layout. Then I started searching for other layouts and found dvorak, colemak, workman etc. All of them were designed to offer a better typing experience for English typists. When I am on my computer, I mostly type code so I didn't bother to look for better alternatives for Turkish layouts such as F. I decided to use dvorak because it has a variant which is designed specifically for programmers such that you don't have to press Shift to type symbols. I liked it very much. Everything was perfect -- almost. In programmer dvorak:

- You can type symbols without pressing Shift but the order of opening and closing pairs is not consistent. Here is the number/symbol row so you can understand me better: `$&[{}(=*)+]!#` Why the curly braces are next to each other and not on different hands like in square brackets and parenthesis? Who thought this was a good idea?
- Normal dvorak layout does not change the order of numbers. But the person who designed the programmer dvorak decided to make numbers alternating between left and right hand. Odd numbers on the left and evens on the right: `~%7531902468` I didn't really mind this at first but couldn't get used to it. On a split keyboard, numbers goes like this: `~%7531  902468` and it is very frustrating that 9 is on the other side. I didn't want to reprogram my keyboard because sometimes I use my laptop's keyboard and I didn't want to make my life any harder. 

These two were the biggest problems of programmer dvorak for me. I tried my best to get used to it but it really didn't worth. Since I was using an English layout, typing in Turkish was very hard because I had to switch to Turkish layout type 1 character and switch back again. Too much pain. I decided to write my own layout and get rid of all the problems -- and create a new problem because I won't be able to find my layout on another computer. Nevertheless, I think it is not that much of a big problem because even if need to use some other computer one day, adding the new layout will not be that hard. That's why I'm writing these little TIL's. 

## Creating the layout

I used three resources to create my own layout. Here are the links: [one](https://www.linux.com/news/creating-custom-keyboard-layouts-x11-using-xkb/), [two](http://karols.github.io/blog/2013/11/18/creating-custom-keyboard-layouts-for-linux/) and [three](https://wiki.archlinux.org/title/X_keyboard_extension). Here are the notes from my side: 

- The `xkb` directory was located at `/usr/share/X11/xkb/` on my machine.
- If you want to create a variant instead of a new layout, just modify the original layout and put your variant there. For example, I want to create a new variant for us layout so I modified this file: `/usr/share/X11/xkb/symbols/us`
- If a variant has default keyword, it is the default variant for that layout. I didn't try this yet but it might be useful in the future.
- A key generate up to 4 different symbols in a usual scenario: normal, Shifted, AltGr'ed, AltGr+Shift'ed. Here is how is my c key configured: c, C, ccedilla, Ccedilla.
- In order to make AltGr work as intended, you need to `include "level3(ralt_switch)"` at the start of your variant.
- You can make any key to act as if Shift being pressed when Caps Lock is active. What do I mean? Suppose you are writing an `UPPERCASE_CONSTANT` in some programming language. In normal scenario, you can either hold Shift and type everything or press caps lock and type until `_` character and type it using Shift and continue with the rest. Have you ever thought why alphabet characters becomes shifted but not the symbols when caps lock is on? What if you just press `-` and it would be a `_` if the caps lock is active? `type[Group1] = "FOUR_LEVEL_ALPHABETIC"` add this to key definition? and you will be good to go.
- When you are done configuring your layout, add it to `/usr/share/X11/xkb/rules/xfree86.lst` so that you can use `setxkbmap` to select your layout/variant.
- You also need to add it to `/usr/share/X11/xkb/rules/evdev.xml`, otherwise `localectl` utility won't be able to find your layout.

## Result

![My gorgeous layout](https://raw.github.com/Asocia/til/master/img/keyboard-layout.jpg)

Look at this. It is a masterpiece! 
- Number row makes sense, no stupid bracket placement or alternating numbers. 
- The keys and their shifted versions are logical from a vim user perspective.
  - I can search forward with `/` and search backward with `?`. And `?` is `Shift+/`! 
  - I can search forward for the word under cursor with `*` and backward with `#` and one is also shifted version of the other.
  - I need to press `^` to move the beginning of the line and press `$` to move the end of the line. These characters are also used by the regex engines to match start or end of line. They are on the same key.
- Related keys are next to each other so they are easier to remember and type. 
  - A shebang starts with `#!` characters, these keys are next to each other. Very satisfying to type :D
  - In C/C++ when doing pointer related things `*` and `&` is used a lot. These keys are also next to each other.
- I can type Turkish characters by pressing AltGr. 

I wish I had done this before. This is just too much power! 

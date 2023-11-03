This is archive of a reddit post of mine: [Send a specific key before every keypress on certain layer](https://www.reddit.com/r/olkb/comments/qla8l1/send_a_specific_key_before_every_keypress_on/)

---


## Problem:

> Hi all, I'm configuring my Sofle and there is just one thing left that I couldn't manage to do by reading the docs. Here is the case:

> I want to send `Ctrl-v` before every keypress if I'm on a certain layer. If I press `a` on that layer, the keyboard should send `Ctrl-v` then `a`. I think this should be possible to do using macros as the documentation states "Macros allow you to send multiple keystrokes when pressing just one key." However, I just couldn't find a way to implement it. Can you just give me simple example to start with?

> If you are curious why would anyone needs such functionality: the web extension I'm using (tridactyl) have different modes (normal, ignore etc.) and `Ctrl-v` sends me to the ignore mode for just one keypress. If I want to send multiple commands in ignore mode, I can either switch to ignore mode or press `ctrl-v` and the key I want to send. I usually want to stay in normal mode. So I wanted to create a layer on my keyboard and switch to that layer when I want to send commands in ignore mode.


## Solution:
> I figured it out! I have created a new layer and set a flag when I switched to it. Then inside `process_record_user` I checked for the flag and if that's the case sent `Ctrl-v` before the keypress.

```
bool is_youtube_layer = false;
layer_state_t layer_state_set_user(layer_state_t state){
    switch (get_highest_layer(state)) {
        case _YOUTUBE:
            is_youtube_layer = true;
            break;
        default:
            is_youtube_layer = false;
    }
    return state;
}

uint8_t mod_state;

bool process_record_user(uint16_t keycode, keyrecord_t *record) {
    mod_state= get_mods();
    if (is_youtube_layer){
        switch (keycode) {
          case KC_A ... KC_Z:
            if (record->event.pressed){
              clear_mods();
              tap_code16(C(KC_V));
              set_mods(mod_state);
              register_code(keycode);
            } else {
              unregister_code(keycode);
            }
            return false;
        }
    }
    switch (keycode) {
     ...
   }
}
```

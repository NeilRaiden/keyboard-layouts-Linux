# Keyboard Layouts for Linux

Phonemic keyboard layouts for Linux for typing in English phonemically.

## Installation

```
sudo mkdir -p /etc/xkb/rules
sudo mkdir -p /etc/xkb/symbols
sudo cp evdev evdev.xml /etc/xkb/rules/
sudo cp writer /etc/xkb/symbols/
sudo ln -s /etx/xkb/symbols/writer /usr/share/X11/xkb/symbols/writer
```

> Note: in GNOME the `evdev` file is ignored. Only `evdev.xml` is required.

## Testing symbols file

There is no such thing as a tool for testing XKB layouts.
The only way is to load the new layout using command line tool `setxkbmap`, and simply type in a text editor to verify that the keystrokes produce desired symbols:

```
setxkbmap -layout filename -variant qwerty
```

Where:
* `filename` is the name of the file containig new layout and either placed or linked to in `/usr/share/X11/xkb/symbols/filename`
* `qwerty` is the string defined in the `filename` with `xkb_symbols "qwerty" {`.

> Hint: before testing run `setxkbmap us`, then `setxkbmap -layout newlayout`. If the new layout does not produce symbols of the Latin alphabet, to restore old layout simply press Escape then use arrow keys to find `setxkbmap us` in the command history.

---



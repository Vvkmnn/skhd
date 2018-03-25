# vHotkeyDaemon

A preservative fork of one of my favorite hotkey managers: [skhd](https://github.com/Vvkmnn/vHotkeyDaemon). All credit goes to the original author(s).

### Building

On macOS `10.13.1`:

Requires xcode-8 command line tools.

```sh
git clone https://github.com/vvkmnn/vHotkeyDaemon.git
make install 
```

### Setting

`skhd` will look for a configuration file `$HOME/.skhdrc`, unless otherwise specified. I use [mine](https://github.com/Vvkmnn/dotfiles/blob/master/.skhdrc), which also has bindings for `chunkwm`, [my favorite window manager!](https://github.com/Vvkmnn/vWindowDaemon)

A hotkey is written according to the following rules:

```
hotkey   = <keysym> ':' <command> |
           <keysym> '->' ':' <command>

keysym   = <mod> '-' <key> | <key>

mod      = 'built-in mod keyword' | <mod> '+' <mod>

key      = <literal> | <keycode>

literal  = 'single letter or built-in keyword'

keycode  = 'apple keyboard kVK_<Key> values (0x3C)'

->       = keypress is not consumed by skhd

command  = command is executed through '$SHELL -c' and
           follows valid shell syntax. if the $SHELL environment
           variable is not set, it will default to '/bin/bash'.
           when bash is used, the ';' delimeter can be specified
           to chain commands.

           to allow a command to extend into multiple lines,
           prepend '\' at the end of the previous line.

           an EOL character signifies the end of the bind.

```

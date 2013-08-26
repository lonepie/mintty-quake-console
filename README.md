# mintty-quake-console

A little [AutoHotkey](http://www.autohotkey.com/) script that enables a quake-style console for [mintty](http://code.google.com/p/mintty/) (like [Visor](http://visor.binaryage.com/) for OS X)

## Requirements
- [mintty](http://code.google.com/p/mintty/) (installed through [Cygwin](http://www.cygwin.com) or [MSYS](http://www.mingw.org/wiki/MSYS))

## Usage
download and run **mintty-quake-console.exe**

right click icon in system tray -> "Options"

press **ctrk + ~** (or configured keybinding) to toggle console

note: after manually changing the ini file, reload the script by right-clicking the tray icon and selecting **Reload**

## Ini/Option Reference
**mintty_path** = path to mintty.exe  

**mintty_args** = arguments to pass to mintty.exe  

**hotkey** = key combination to show/hide console

**start_with_windows** = add this script to Windows startup (1) or disable (0)

**start_hidden** = show mintty.exe when script is started (0) or wait for hotkey (1)  

**initial_height** = height (in pixels) of the mintty console  

**initial_width** = width (percentage of screen width) of the mintty console  

**initial_trans** = transparency (range from 0 to 255) of the mintty console  

**autohide_by_default** = set to 1 to automatically hide mintty when it loses focus

**animation_step** = number of pixels to shift each step of the slide animation  

**animation_timeout** = how long (in ms) to wait between each animation_step

**animation_mode_slide** = set to 1 to use sliding animation (up/down)

**animation_mode_fade** = set to 1 to use fading animation (in/out)

## Tips

Use **Ctrl+Alt+Numpad(+/-)** to increase or decrease the console height

To use ZSH instead of BASH, set the following in mintty-quake-console.ini (zsh must be installed through cygwin):

	mintty_args=/bin/zsh -li

Download my [minttyrc](https://github.com/lonepie/dotfiles/raw/master/minttyrc) for my font/color settings

	$ wget -O ~/.minttyrc https://github.com/lonepie/dotfiles/raw/master/minttyrc

## TO DO
* pseudo-tabs implementation
* create a port for puTTY/kiTTY
* a port for Console2 or ConEmu?

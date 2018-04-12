
# About mintty-quake-console

This AutoHotKey script implements a hotkey for Quake&trade; console-like dropdown support for the [mintty terminal emulator](https://github.com/mintty/) on Windows.

## Requirements

- [mintty](https://github.com/mintty/) (installed through [Cygwin](http://www.cygwin.com), [MSYS](http://www.mingw.org/wiki/MSYS) or [wsltty](https://github.com/mintty/wsltty))

## Usage

[Download latest release](https://github.com/lonepie/mintty-quake-console/releases) and run `mintty-quake-console.exe` **OR**, if you have AutoHotkey installed, clone the repository and run the `mintty-quake-console.ahk` script directly.

**Options:** Right click the mintty-quake-console icon in system tray & select _Options_.

Press `Ctrl ~` (or configured keybinding) to toggle mintty.

**Note:** after editing the ini file by hand, reload the script by right-clicking the tray icon and selecting _Reload_.

## Screenshots

![mintty-quake-console Screenshot](https://lonepie.github.io/mintty-quake-console/assets/img/2018-03-05_18-08-57.png)
![mintty-quake-console Screencap](https://lonepie.github.io/mintty-quake-console/assets/img/optimized.gif)
*Note: the animation is much more fluid than shown here (the capture software didn't play nice with it).*

## Ini/Option Reference

**mintty_path** = path to mintty.exe

**mintty_args** = arguments to pass to mintty.exe

**hotkey** = key combination to show/hide console ([AutoHotkey format](https://www.autohotkey.com/docs/Hotkeys.htm) & [Keylist](https://www.autohotkey.com/docs/KeyList.htm))

**start_with_windows** = add this script to Windows startup (1) or disable (0). *Default: 0*

**start_hidden** = show mintty.exe when script is started (0) or wait for hotkey (1). *Default: 1*

**initial_height** = height (in pixels) of the mintty console. *Default: 380*

**initial_width** = width (percentage of screen width) of the mintty console. *Default: 100*

**initial_trans** = transparency (range from 0 to 255) of the mintty console. *Default: 235*

**autohide_by_default** = set to 1 to automatically hide mintty when it loses focus. *Default: 1*

**animation_step** = number of pixels to shift each step of the slide animation. *Default: 20*

**animation_timeout** = how long (in ms) to wait between each animation_step. *Default: 10*

**animation_mode_slide** = set to 1 to use sliding animation (up/down). *Default: 0*

**animation_mode_fade** = set to 1 to use fading animation (in/out). *Default: 1*

**window_borders** = set to 1 to keep window borders & title bar on mintty. *Default: 0*

**display_on_monitor** = in multiple-monitor setups, the monitor that mintty will appear on. 0 will make mintty display on whichever monitor the mouse cursor currently resides on. 1 for primary display, 2 for secondary, etc. *Default: 0*

## Tips

### Local Configuration File

Support for `mintty-quake-console.local.ini` file (also in .gitignore), so you can have a custom config without dirtying the repository.

### Edit Config Directly

Added a menu entry to directly edit the config file with notepad (or whatever is defined by %EDITOR% env var)

### Additional Hotkeys

**Ctrl+Alt+Numpad(+)** increase console height

**Ctrl+Alt+Numpad(-)** decrease console height

**Ctrl+Alt+]** increase console width

**Ctrl+Alt+[** decrease console width

**Ctrl+Alt+Numpad(/)** toggle window borders and titlebar

**Ctrl+Alt+Numpad(*)** saves height, width & window borders state

**Ctrl+Alt+Numpad(.)** toggle script

### Use with [wsltty](https://github.com/mintty/wsltty)

Essentially, copy the command line from the shortcut(s) created by wsltty and split the path and the arguments:

```ini
mintty_path=%LOCALAPPDATA%\wsltty\bin\mintty.exe
mintty_args=--WSL= --configdir="%APPDATA%\wsltty" -~
```

#### wsltty non-default shell

To run a different shell without changing WSL's default shell, append shell path to `mintty_args`:

```ini
mintty_args=--WSL= --configdir="%APPDATA%\wsltty" -~ /usr/bin/fish -li
```

#### Cygwin non-default shell

To use ZSH instead of BASH, set the following in mintty-quake-console.ini (zsh must be installed through cygwin):

```ini
mintty_args=/bin/zsh -li
```

### Tabs

Use a terminal multiplexer, like [tmux](https://github.com/tmux/tmux/wiki) *(recommended)* or [screen](https://www.gnu.org/software/screen/).

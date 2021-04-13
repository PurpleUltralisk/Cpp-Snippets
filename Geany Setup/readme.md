# Geany IDE Setup

## Install
`sudo apt install geany`
`sudo apt install g++`

## Preference Setup 
In `Keybindings` tab, set `Switch to Editor` as `F1` and confirm overriding, then `Switch to VTE` as `F2` (VTE is built-in terminal).

In `Terminal tab`, mark `Follow path of the current file`. 
Terminal will now automatically change a path after you open a new file.

## Build Command
Open any C++ file in Geany, go to Build -> Set Build Commands and copy these flags.
Compile (F8): `g++ -std=c++17 -Wshadow -Wall -o "%e" "%f" -O2 -Wno-unused-result`
Build (F9): `g++ -std=c++17 -Wshadow -Wall -o "%e" "%f" -g -fsanitize=address -fsanitize=undefined -D_GLIBCXX_DEBUG`

## Colorful terminal
Open file `~/.bashrc` and uncomment line `#force_color_prompt=yes` in order to get colorful terminal in Geany. 
In the same file, add a line `ulimit -s 2000123` to set the stack limit to around 2GB. 
Restart geany (or your PC) or run `source ~/.bashrc` to trigger the change.

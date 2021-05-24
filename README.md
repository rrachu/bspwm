## BSPWM Dotfiles
Repository containing all my configuration files used to create my rice. Below an example of the final result. <br>Linux Mint, Ubuntu and Debian based.

![image](example.png)
---

### How to install

First of all
```sh
sudo apt update
sudo apt full-upgrade -y
sudo apt clean
sudo apt autoremove -y
sudo apt autoclean
```

Dependencies
```sh
sudo apt install -y build-essential cmake cmake-data pkg-config libcairo2-dev libxcb1-dev libxcb-util0-dev libxcb-randr0-dev libxcb-composite0-dev python3-xcbgen xcb-proto libxcb-image0-dev libxcb-ewmh-dev libxcb-icccm4-dev libcurl4-openssl-dev libjsoncpp-dev libpulse-dev libmpdclient-dev libasound2-dev libxcb-cursor-dev libxcb-xrm-dev libxcb-xkb-dev libnl-genl-3-dev
```
Packages
```sh
sudo apt install -y bspwm sxhkd subversion rofi feh numlockx compton dunst neofetch imagemagick webp unifont xfce4-terminal git arc-theme papirus-icon-theme
```

### Install polybar

```sh
sudo apt update
```
```sh
sudo apt install cmake cmake-data libcairo2-dev libxcb1-dev libxcb-ewmh-dev libxcb-icccm4-dev libxcb-image0-dev libxcb-randr0-dev libxcb-util0-dev libxcb-xkb-dev pkg-config python3-xcbgen xcb-proto libxcb-xrm-dev libasound2-dev libmpdclient-dev libiw-dev libcurl4-openssl-dev libpulse-dev
```
```sh
sudo apt install libxcb-composite0-dev && sudo apt install libjsoncpp-dev
sudo ln -s /usr/include/jsoncpp/json/ /usr/include/json
```
```sh
git clone https://github.com/polybar/polybar
```
```sh
cd polybar && ./build.sh
```
Be careful to type 'N' when the build asks if you want to download the example polybar configuration.

## Applying the settings

```sh
git clone https://github.com/terroo/fonts.git
cd fonts/fonts && cp *.ttf *.otf $HOME/.local/share/fonts/
fc-cache -fv
```

```sh
cd $HOME/bspwm # this if you cloned the repository in your home
```
```sh
mv bspwm/ ${HOME}/.config/
mv sxhkd/ ${HOME}/.config/
mv dunst/ ${HOME}/.config/
mv polybar/ ${HOME}/.config/
mv rofi/ ${HOME}/.config/
mv wallpaper.jpg ${HOME}/.wallpaper.jpg
feh --bg-scale ${HOME}/.wallpaper.jpg # set wallpaper
```
Now just logout.

#### Extras
To change the name of your polybar distro, just edit the file.
``$HOME/.config/polybar/user_modules.ini``
And switch to your distro's logo. 

Distro  | Text for Polybar
------- | ----------------
Linux Mint |  Linux Mint
Ubuntu |  Ubuntu
Debian |  Debian

It is very likely that the characters are not appearing here in the repository. But rest assured, if you installed all fonts correctly, the font will appear on the polybar when you paste

### Some keyboard shortcuts
You can edit them in the ``.config/sxhkd/sxhkdrc`` file.

Shortcut  | Exec
--------  | ------
super + Return | Terminal
super + shift + i | Flameshot
super + d | Rofi
super + alt + r | Restart bspwm
super + {Left,Down,Up,Right} | Changes the window in focus
super + shift + u | MPD

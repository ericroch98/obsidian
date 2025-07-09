#config #dotfiles 
1.
```bash
sudo apt install uuid-dev libdbus-1-dev libxcursor-dev libxrandr-dev libxi-dev libxinerama-dev libgl1-mesa-dev libxkbcommon-x11-dev libfontconfig-dev libx11-xcb-dev
```
2.
```bash
git clone https://github.com/kovidgoyal/kitty.git && cd kitty
./dev.sh build
```
3.
```bash
sudo ln -s $(pwd)/launcher/kitty /usr/bin/kitty
sudo ln -s $(pwd)/launcher/kitten /usr/bin/kitten
```

# Devlix WM 1.0 (`dwm` Fork)

## Table of contents :

* Description
    * Patches
    * Key binds
    * Images
* Installation
    * Steps
    * Wallpapers
* To do
* Credits

## Description

This is my setup with a lot of changes in `dwm`, `dmenu`, `dwmblocks` by torrinfail, the configurations and a lot of patches applied.

### Patches

#### List of patches applied (`dwm`)
| File Name & Path | Readme |
|-------------|--------|
|[dwm-6.2-urg-border.diff](dwm/patch/dwm-6.2-urg-border.diff)|[https://dwm.suckless.org/patches/urgentborder/](https://dwm.suckless.org/patches/urgentborder/)|
|[dwm-alwayscenter-20200625-f04cac6.diff](dwm/patch/dwm-alwayscenter-20200625-f04cac6.diff)|[https://dwm.suckless.org/patches/alwayscenter/](https://dwm.suckless.org/patches/alwayscenter/)|
|[dwm-attachbelow-6.2.diff](dwm/patch/dwm-attachbelow-6.2.diff)|[https://dwm.suckless.org/patches/attachbelow/](https://dwm.suckless.org/patches/attachbelow/)|
|[dwm-autostart-20210120-cb3f58a.diff](dwm/patch/dwm-autostart-20210120-cb3f58a.diff)|[https://dwm.suckless.org/patches/autostart/](https://dwm.suckless.org/patches/autostart/)|
|[dwm-cursorwarp-6.3.diff](dwm/patch/dwm-cursorwarp-6.3.diff)|[https://dwm.suckless.org/patches/cursorwarp/](https://dwm.suckless.org/patches/cursorwarp/)|
|[dwm-fullgaps-6.4.diff](dwm/patch/dwm-fullgaps-6.4.diff)|[https://dwm.suckless.org/patches/fullgaps/](https://dwm.suckless.org/patches/fullgaps/)|
|[dwm-movestack-20211115-a786211.diff](dwm/patch/dwm-movestack-20211115-a786211.diff)|[https://dwm.suckless.org/patches/movestack/](https://dwm.suckless.org/patches/movestack/)|
|[dwm-pertag-20200914-61bb8b2.diff](dwm/patch/dwm-pertag-20200914-61bb8b2.diff)|[https://dwm.suckless.org/patches/pertag/](https://dwm.suckless.org/patches/pertag/)|

#### List of patches applied (`dmenu`)
| File Name & Path | Readme |
|-------------|--------|
|[dmenu-alpha-20230110-5.2.diff](dmenu/patch/dmenu-alpha-20230110-5.2.diff)|[https://tools.suckless.org/dmenu/patches/center/](https://tools.suckless.org/dmenu/patches/center/)|
|[dmenu-center-20240616-36c3d68.diff](dmenu/patch/dmenu-center-20240616-36c3d68.diff)|[https://tools.suckless.org/dmenu/patches/center/](https://tools.suckless.org/dmenu/patches/center/)|
|[dmenu-numbers-20220512-28fb3e2.diff](dmenu/patch/dmenu-numbers-20220512-28fb3e2.diff)|[https://tools.suckless.org/dmenu/patches/numbers/](https://tools.suckless.org/dmenu/patches/numbers/)|

### Images
| 1 | 2 |
|---|---|
|![devlix](screenshots/scrot1.png)|![devlix](screenshots/scrot2.png)|


## Installation

**Warning: I will assume this is a brand new minimal arch linux installation**

**If you are doing this on virtual box enable 3d acceleration**

### Steps

1. Install these packages

```bash
sudo pacman -Syu alacritty xorg-server xorg-xinit xorg-xsetroot xorg-xrandr feh picom python-pywal neofetch lf ueberzug ffmpegthumbnailer imagemagick poppler base-devel git bat chafa unzip p7zip unrar catdoc docx2txt odt2txt gnumeric zsh vim go webkit2gtk libxft libxinerama libx11 ttf-jetbrains-mono-nerd alsa-utils scrot python3 networkmanager
```

```bash
git clone https://aur.archlinux.org/yay.git
cd yay
makepkg -si
cd ..
yay -Syu epub-thumbnailer-git wkhtmltopdf-static 7-zip
```

2. `Git clone` this repository

```bash
git clone https://github.com/Mohamed1242012/suckless.git
```

3. Set the wallpaper by `wal`
```
cd suckless
wal -i wallpapers/[img name]
cd alacritty-color-export/
./script.sh
cd ..
```

#### Available Wallpapers
| Name | IMG | Name | IMG |
|------|-----|------|-----|
| walll1.jpg | ![wall1.jpg](wallpapers/wall1.jpg) | wall2.png | ![wall2.png](wallpapers/wall2.png) |
| walll3.png | ![wall3.png](wallpapers/wall3.png) | wall4.png | ![wall4.png](wallpapers/wall4.png) |
| wall5.jpg | ![wall5.jpg](wallpapers/wall5.jpg) |

4. Build

```bash
cd dwm
sudo make clean install
cd ..
cd dmenu
sudo make clean install
cd ..
cd dwmblocks
sudo make clean install
cd ..
```

5. Put all configs into place

```bash
rm -rf ~/.config/wal
cp -r configs/* ~/.config/
```

6. Set `zsh` as default shell

```bash
chsh -s /usr/bin/zsh
exit
```
Now login
Then press 1 then 2 then 1 then 0

7. Install `ohmyzsh`

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
exit
exit
```
Now login

8. Install `zsh` plugins and `powerlevel10k`

```bash
git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions

git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting

git clone https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
```

9. Putting more configs into place

```bash
cp suckless/.zshrc ~/.zshrc
cp suckless/.zprofile ~/.zprofile
cp suckless/.xinitrc ~/.xinitrc
cp suckless/.p10k.zsh ~/.p10k.zsh
```

8. `lf` image support

```bash
cd suckless/lfimg
sudo make clean install
```

9. Finally

```bash
exit
```
Now login

#### And You should be greeted with Devlix WM

---

### To Do

- [ ] Make an installer script
- [ ] Add key binds page
- [x] Fix freezing on virtual box
- [ ] Add support for multilingual keyboards other than Arabic
- [ ] Add it to the `AUR`
- [ ] Making a `vim` config
- [x] Audio key bind script
- [x] Brightness key bind script
- [ ] Adding a clipboard manager (`clipmenu` - integration with `dmenu`)
- [ ] Adding a notification manager
- [ ] Making a change background script
- [ ] Organizing the project more
- [ ] Finding a contributor :\
- [ ] Adding `slstatus` patch to `dwm`
- [ ] Make a documentation
- [ ] Make a wiki
- [ ] Make a website
- [ ] Add more photos and videos
- [ ] Make a YouTube channel
- [ ] Post on r/unix port
- [ ] Making a more descriptive `README.md`

---

### Credits
[LICENSE](LICENSE)

This open source project wouldn't be possible without these people and there open source projects:
- [https://github.com/egeesin/pywal2alacritty](https://github.com/egeesin/pywal2alacritty)
- [https://git.suckless.org/dwm](https://git.suckless.org/dwm)
- [https://git.suckless.org/dmenu](https://git.suckless.org/dmenu)
- [https://github.com/dylanaraps/pywal](https://github.com/dylanaraps/pywal)
- [https://github.com/torrinfail/dwmblocks](https://github.com/torrinfail/dwmblocks)
- [https://github.com/thimc/lfimg](https://github.com/thimc/lfimg)
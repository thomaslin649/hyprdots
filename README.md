# --// Hyprdots //--

## My Arch Hyprland Config Files

> **Warning**
>
> Install script will auto-detect nvidia card and install nvidia-dkms drivers for your kernel.
> Nvidia drm will be enabled only in grub and Hyperland is launched by sddm!!


### Showcase
https://user-images.githubusercontent.com/106020512/235429801-e8b8dae2-c1ad-4e23-9aa2-b1edb6cabe99.mp4

|     |     |
| --- | --- |
![](https://raw.githubusercontent.com/prasanthrangan/hyprdots/main/Source/screenshot_1.png) | ![](https://raw.githubusercontent.com/prasanthrangan/hyprdots/main/Source/screenshot_2.png)
![](https://raw.githubusercontent.com/prasanthrangan/hyprdots/main/Source/screenshot_3.png) | ![](https://raw.githubusercontent.com/prasanthrangan/hyprdots/main/Source/screenshot_4.png) 


### Installation
After minimal Arch install (with grub), clone and execute -
```shell
pacman -Sy git
git clone https://github.com/prasanthrangan/hyprdots ~/Dots
cd ~/Dots/Scripts
./install.sh
```

> **Note**
>
> You can also create your own file (for ex. custom_app.lst) with all your favorite apps and pass the file as a parameter to install it -
>```shell
>./install.sh custom_app.lst
>```
> Please reboot after the install script completes and takes you to sddm login screen for the first time.


### Theming
To add your own custom theme, please refer [Theming.md](https://github.com/prasanthrangan/hyprdots/blob/main/Theming.md)
- Available themes
    - [x] Catppuccin-Mocha
    - [x] Catppuccin-Latte
    - [x] Decay-Green
    - [ ] Tokyo-Night
    - [ ] Rosé-Pine


<details>
<summary><h4>Packages</h4></summary>

| nvidia | |
| --- | --- |
linux-headers | for main kernel (script will auto detect from /usr/lib/modules/)
linux-zen-headers | for zen kernel (script will auto detect from /usr/lib/modules/)
linux-lts-headers | for lts kernel (script will auto detect from /usr/lib/modules/)
nvidia-dkms | nvidia drivers (script will auto detect from lspci -k | grep -A 2 -E "(VGA|3D)")
nvidia-utils | nvidia drivers (script will auto detect from lspci -k | grep -A 2 -E "(VGA|3D)")

| tools | |
| --- | --- |
pipewire | audio and video server
pipewire-alsa | for audio
pipewire-audio | for audio
pipewire-jack | for audio
pipewire-pulse | for audio
gst-plugin-pipewire | for audio
wireplumber | audio and video server
networkmanager | network manager
network-manager-applet | nm tray
bluez | for bluetooth
bluez-utils | for bluetooth
blueman | bt tray

| login | |
| --- | --- |
sddm-git | display manager for login
qt5-wayland | for QT wayland XDP
qt6-wayland | for QT wayland XDP
qt5-quickcontrols | for sddm theme
qt5-quickcontrols2 | for sddm theme
qt5-graphicaleffects | for sddm theme

| hypr | |
| --- | --- |
hyprland-git | main window manager (script will change this to hyprland-nvidia-git if nvidia card is detected)
dunst | graphical notification daemon
rofi-lbonn-wayland-git | app launcher
waybar-hyprland-git | status bar
swww | wallpaper app
swaylock-effects-git | lockscreen
wlogout | logout screen
grim | screenshot tool
slurp | selects region for screenshot/screenshare
swappy | screenshot editor
cliphist | clipboard manager

| dependencies | |
| --- | --- |
polkit-kde-agent | authentication agent
xdg-desktop-portal-hyprland-git | XDG Desktop Portal
imagemagick | for kitty/neofetch image processing
qt5-imageformats | for dolphin thumbnails
pavucontrol | audio settings gui
pamixer | for waybar audio

| theming | |
| --- | --- |
nwg-look | theming GTK apps
kvantum | theming QT apps
qt5ct | theming QT5 apps

| applications | |
| --- | --- |
firefox | browser
kitty | terminal
neofetch | fetch tool
dolphin | kde file manager
visual-studio-code-bin | gui code editor
vim | text editor
ark | kde file archiver

| shell | |
| --- | --- |
zsh | main shell
exa | colorful file lister
oh-my-zsh-git | for zsh plugins
zsh-theme-powerlevel10k-git | theme for zsh
zsh-syntax-highlighting-git | highlighting of commands
zsh-autosuggestions-git | see completion as you type
pokemon-colorscripts-git | display pokemon sprites

</details>


<details>
<summary><h4>Keybindings</h4></summary>

| Key 1 | Key 2 | Key 3 | Action |
| :-:   | :-:   | :-:   | ---    |
| `Super` | `Q` | | Quit active/focused window
| `Super` | `del` | | quit Hyprland session
| `Super` | `W` | | toggle Window on focus to float
| `Alt` | `enter` | | toggle window on focus to fullscreen
| `Super` | `G` | | disable hypr effects for Gamemode
| `Super` | `T` | | launch kitty Terminal
| `Super` | `E` | | launch dolphin file Explorer
| `Super` | `V` | | launch Vs code
| `Super` | `F` | | launch Firefox
| `Super` | `A` | | launch desktop Applications (rofi)
| `Super` | `tab` | | switch open applications (rofi)
| `Super` | `R` | | browse system files (rofi)
| `F10` | | | mute audio output
| `F11` | | | decrease volume
| `F12` | | | increase volume
| `Super` | `L` | | lock screen
| `Super` | `backspace` | | logout menu
| `Super` | `P` | | screenshot snip
| `Super` | `Alt` | `P` | print current screen and save to ~/Apps/grim/

</details>


<details>
<summary><h4>Playlist</h4></summary>

[![IMAGE ALT TEXT](http://img.youtube.com/vi/_nyStxAI75s/0.jpg)](https://www.youtube.com/watch?v=_nyStxAI75s&list=PLt8rU_ebLsc5yEHUVsAQTqokIBMtx3RFY)

</details>


<details>
<summary><h4>To-Do</h4></summary>

- [x] Wallpaper change script (ver2)
- [x] Theme selector script
- [x] Theme change script (ver2)
- [x] Update rofi configs
- [x] Clipboard manager in waybar
- [ ] Add options to install script (ver2)
- [ ] Update Volume control script/notification (ver2)
- [ ] Media control for waybar? (maybe later)
- [ ] Replace waybar with Eww? (maybe later)

</details>


<details>
<summary><h4>Known Issues</h4></summary>

- [ ] Random lockscreen crash, refer https://github.com/swaywm/sway/issues/7046
- [ ] Waybar launching rofi breaks mouse input (added `sleep 0.1` as workaround), refer https://github.com/Alexays/Waybar/issues/1850
- [ ] Flatpak Gnome Boxes needs xdg-desktop-portal-gtk
- [ ] Flatpak QT apps does not follow system theme

</details>


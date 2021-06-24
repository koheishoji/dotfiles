# dotfiles

I'm using Manjaro Linux KDE edition, so describe how to install packages on Manjaro Linux.

## **How to symbolic link**

After installing a certain package, please run the following command

```bash
./<package_name>/symbolic.sh
```

## **How to install**

## [prezto](https://github.com/sorin-ionescu/prezto)

Clone the repository:

```bash
git clone --recursive https://github.com/sorin-ionescu/prezto.git "${ZDOTDIR:-$HOME}/.zprezto"
```

Create a new Zsh configuration by copying/linking the Zsh configuration files provided:

```bash
setopt EXTENDED_GLOB
for rcfile in "${ZDOTDIR:-$HOME}"/.zprezto/runcoms/^README.md(.N); do
  ln -s "$rcfile" "${ZDOTDIR:-$HOME}/.${rcfile:t}"
done
```

Set Zsh as your default shell:

```bash
chsh -s /usr/bin/zsh
```

## [nvm](https://github.com/nvm-sh/nvm)

```bash
sudo pacman -S nvm
```

after installed,

```bash
echo ‘## nvm
source /usr/share/nvm/init-nvm.sh’ >> ~/.zshrc
```

## [burpsuite](https://portswigger.net/burp)

```bash
yay -S burpsuite
```

after installed,

```bash
sudoedit /etc/environment
```

Add the following at the end

```/etc/environment
_JAVA_OPTIONS='-Dawt.useSystemAAFontSettings=on'
```

## [alacritty](https://github.com/alacritty/alacritty)

```bash
sudo pacman -S alacritty
```

## [ibus-mozc](https://wiki.archlinux.jp/index.php/IBus)

```bash
yay -S ibus ibus-qt ibus-mozc manjaro-asian-input-support-ibus
```

after installed,

```bash
ibus-setup
qtconfig-qt4
reboot
```

after reboot,

```bash
ibus-deamon --panel=/usr/lib/kimpanel-ibus-panel
./ibus-mozc/symbolic.sh
```

reboot last time

## [libinput-gestures](https://github.com/bulletmark/libinput-gestures)

```bash
sudo gpasswd -a $USER input
sudo pacman -S wmctrl xdotool
sudo pacman -S libinput-gestures
```

after installed,

```bash
libinput-gestures desktop
libinput-gestures autostart
```

## [neovim](https://github.com/neovim/neovim)

```bash
sudo pacman -S neovim python-pynvim
```

## [tmux](https://github.com/tmux/tmux)

```bash
sudo pacman -S tmux
```

## [vim](https://github.com/vim/vim)

```bash
sudo pacman -S vim
```

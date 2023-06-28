# Arch-Linux-KDE-Plasma-Desktop-On-Termux-x11

This is a preinstalled arch-linux distro with KDE plasma
Before you install it , disable phantom process killer.Watch from here.

[Youtube](https://youtu.be/UxmQSETvAOc)

## Preview
![](https://raw.githubusercontent.com/atamshkai/Arch-Linux-KDE-Plasma-Desktop-On-Termux-x11/main/Archlinux%20Plasma%20Desktop.jpg)

# To Do

#### First,Download Debian Distro From Here,

[Link](https://www.mediafire.com/file/kuv961h6vyo4nu8/archlinux.tar.xz/file))

## Installation

Download archlinux.tar.xz to Device's Download folder first.

### Install zsh

```
pkg up -y && pkg i -y zsh wget

wget https://github.com/atamshkai/Termux-Zsh/raw/main/zsh.tar.xz

tar -xvJf zsh.tar.xz && mv zsh/.* ~/ && rm -rf zsh

chsh -s zsh
```

Then,

```
echo "killall pulseaudio &>/dev/null" >>~/.zshrc
```

``` 
echo "pulseaudio --start --exit-idle-time=-1; pacmd load-module module-native-protocol-tcp auth-ip-acl=127.0.0.1 auth-anonymous=1" >>~/.zshrc
```

```
pkg up -y && pkg i -y x11-repo && pkg i -y proot-distro pulseaudio termux-x11-nightly
```

``` 
termux-setup-storage
```

``` 
proot-distro restore /sdcard/download/archlinux.tar.xz
```

```
exit
```

Login again to terminal

Before login to proot,start termux-x11 first.
 
```
termux-x11 :1
```
 
Then,open another session & login
 
```
proot-distro login archlinux --shared-tmp
```
 
Then
 
```
export PULSE_SERVER=127.0.0.1;env DISPLAY=:1 dbus-launch --exit-with-session xfce4-session
```
 
OR 
 
```
tm-x11
```

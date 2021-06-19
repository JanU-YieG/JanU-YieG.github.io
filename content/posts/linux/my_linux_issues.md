---
title: "my linux issues"
date: 2021-05-27T01:17:47+08:00
draft: false
description:
weight: 1
featuredImage: "https://cdn5.maocdn.cn/img/2021/06/15/wp2618282-blackarch-wallpaper.png"
featuredImagePreview: "https://cdn5.maocdn.cn/img/2021/06/15/wp2618282-blackarch-wallpaper.png"
categories:
- Linux
- Hunt
tags:
- linux-issues
- linux
keywords:
- linux-issues
- linux
readingTime: "5"
showTags: true
summary: "solved linux issues in the process when i am using linux"
---
## arch sway

**you can see the [sway wiki page](https://github.com/swaywm/sway/wiki)**

**issue:**
```
[sway-1.0-beta.2/sway/main.c:209] Unable to drop root (we shouldn't be able to restore it after setuid), refusing to start
```
**solved:**
write the following code in your `.bash_profile`
```
if [ -z "${XDG_RUNTIME_DIR}" ]; then
    export XDG_RUNTIME_DIR=/tmp/${UID}-runtime-dir
    if [ ! -d "${XDG_RUNTIME_DIR}" ]; then
    mkdir "${XDG_RUNTIME_DIR}"
    chmod 0700 "${XDG_RUNTIME_DIR}"
    fi
fi
```

**issue**:
can not change brightness
**solved**:
you can use(please use the tools based the wayland protocol) the light to change brightness
```
sudo light -U 10
sudo light -A 10
```

**issue**
```
Could not find the Qt platform plugin “wayland”
```
**solved**:
add environment variables into /etc/environment:
```
QT_QPT_PLATFORM=wayland
```
and install:
qt5-wayland

but some applications based X11 you should set the environment variable QT_QPT_PLATFORM like goldendict below

**issue**:goldendict crashed on wayland

you can see [this page](https://wiki.archlinux.org/title/Wayland#Qt)
**solved**:
open goldendict use :
```
QT_QPT_PLATFORM=xcb goldendict
```

**issue**:
```
[drm:amdgpu_job_timedout [amdgpu]] *ERROR* ring sdma0 timeout, signaled seq=239, emitted seq=240
drm:amdgpu_job_timrout ring gfx timeout but soft recovered
```
**rsolved**:
the new linux kernel is bad compatibility for AGU,you can downgrade linux,linux-firmware,mesa:

mesa: 21.0.3 2
linux-firmware: 20210315.3568f96  2
linux: 5.12.2-arch1-1
```
sudo downgrade linux
sudo downgrade linux-firmware
sudo downgrade mesa
//sudo pacman -U /var/cache/pacman/pkg/<your.zst>
```
If your $esp is not /boot,and then your systemd-boot grub has been bad, then:
```
cp /boot/initramfs-linux-fallback.img $esp/
cp /boot/initramfs-linux.img $esp/
cp /boot/vmlinuz-linux $esp/
```

and then reboot

**issue**:
```
Failed to get backlight or LED device 'backlight:acpi_video0': No such device
systemd-backlight@backlight:acpi_video0.service: Failed with result 'exit-code'.
Failed to start Load/Save Screen Backlight Brightness of backlight:acpi_video0.
```
**resolved**:
adding the `acpi_backlight=vendor` in /etc/devault/grub into the line `GRUB_CMDLINE_LINUX_DEFAULT=`
```
GRUB_CMDLINE_LINUX_DEFAULT="acpi_backlight=vendor quiet"
```

**issue**:
```
Failed to set default locale
```
**resolved**:
adding the following code to change the valiables about locale:`login shell` or `/etc/enviroment`
```
LANG=en_US.UTF-8
LC_CTYPE="en_US.UTF-8"
LC_NUMERIC="en_US.UTF-8"
LC_TIME="en_US.UTF-8"
LC_COLLATE="en_US.UTF-8"
LC_MONETARY="en_US.UTF-8"
LC_MESSAGES="en_US.UTF-8"
LC_PAPER="en_US.UTF-8"
LC_NAME="en_US.UTF-8"
LC_ADDRESS="en_US.UTF-8"
LC_TELEPHONE="en_US.UTF-8"
LC_MEASUREMENT="en_US.UTF-8"
LC_IDENTIFICATION="en_US.UTF-8"
LC_ALL="en_US.UTF-8"
```
**issue**:

sway中fcitx5中文输入法在alacritty中不显示界面的问题
**resolved**:

在sway配置文件中启动alacritty使用`WAYLAND_DISPLAY=x11`

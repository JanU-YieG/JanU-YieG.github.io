---
title: "Linux 应用"
date: 2021-06-11T16:45:59+08:00
lastmod: 2021-06-11T16:45:59+08:00
draft: false
author: "Borer"
authorLink: "https://github.com/JanU-YieG"
description: "我经常使用的一些linux工具"
featuredImage: "https://cdn5.maocdn.cn/img/2021/06/18/index.jpg"
featuredImagePreview: "https://cdn5.maocdn.cn/img/2021/06/18/index.jpg"
weight: 1
keywords: ["linux", "linux-tools"]
tags: ["linux", "linux-tools"]
categories: ["Linux","linux-tools"]
lightgallery: true
showTags: true
summary: "记录一些我日常使用的linux工具"
---
## 经常使用的工具:
1. goldendict
2. neovim
3. tmux
4. firefox
5. calibre
6. typora
7. cmus
8. rust
9. navi(rust)
10. ffsend(rust)
11. lsd(rust)
11. du-dust(rust)
12. ranger
13. ucollage
14. cowsay
15. htop
16. wget
17. curl
18. pamixer
19. xrandr
20. neogetch
21. git
22. vlc
23. kdeconnect
24. syncthing
25. trash
26. nautilus
27. ntfs-3g
28. xarchiver
29. iwd
30. audacity
31. evince
32. openarena
33. zoom
33. fzf
33. wps
33. cherrytree
33. flameshot
33. fxitx5
33. mysql-workbench
33. rofi/wofi/dmenu/bemenu
33. mysql-workbench
33. ctags
33. hddtemp
34. lm_sensors
35. wechat-uos

## Linux桌面环境(i3(X) OR sway(wayland/xwayland))
### i3(X)



### sway(wayland)

### teamviewer
1. Unit teamviewerd.service not found.
- 输入：`sudo /opt/teamviewer/tv_bin/teamviewerd -d`直接重启
- 或者想要使用：`sudo teamviewer --daemon stop/start/restart`，则需要建立teamviewer启动脚本到systemd管理中:`sudo ln -s /opt/teamviewer/tv_bin/script/teamviewerd.service /etc/systemd/system/teamviewerd.service`

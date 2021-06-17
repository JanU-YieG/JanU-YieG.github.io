---
title: "Archlinux 驱动"
subtitle: "必备的Archlinux驱动安装和使用"
date: 2021-06-17T17:36:43+08:00
lastmod: 2021-06-17T17:36:43+08:00
draft: false
author: "Borer"
authorLink: "https://github.com/JanU-YieG"
description:
hiddenFromHomePage: false
hiddenFromSearch: false
featuredImage: "https://img.maocdn.cn/img/2021/06/07/728908.jpg"
featuredImagePreview: "https://img.maocdn.cn/img/2021/06/07/728908.jpg"
weight: 1
resources:
- name: ""
  src: "xx.jpg"
keywords: ["Linux", "linux","arch","linux driver","bluetooth"]
tags: ["Archlinux", "Linux-driver"]
categories: ["Archlinux","Linux"]
lightgallery: true
toc:
  enable: true
math:
  enable: false
showTags: true
license: ""
summary: "Archlinux 必要驱动安装和使用教程"
---

<!--more-->

## 无线(wifi)
#### iwd
1. 安装iwd
    ```
    sudo pacman -S iwd
    ```
2. 使用
    - 进入iwd管理
    ```
    iwctl
    ```
    - 命令使用并连接wifi
    ```
    //查看适配器列表
    adapter list
    //查看无线设备
    device list
    //如果没有打开适配器和无限设备则打开
    adapter adapter-name(phy0) set-property Powered on
    device device-name(wlan0) set-property Powered on
    //扫瞄wifi
    station device-name(wlan0) scan
    //显示所有wifi
    station device-name(wlan0) get-networks
    //连接wifi
    station device-name(wlan0) connect wifi-name
    ```

## 蓝牙(bluetooth)
#### bluez
1. 安装bluez和工具
    ```
    sudo pacman -S bluez
    sudo pacman -S bluez-utils
    ```
2. 使用
    - 进入蓝牙管理
    ```
    bluetoothctl
    ```
    - 

---
title: "Git常用功能(github)"
subtitle: "常用的git功能"
date: 2021-06-17T18:45:18+08:00
lastmod: 2021-06-17T18:45:18+08:00
draft: false
author: "Borer"
authorLink: "https://github.com/JanU-YieG"
description: "git 常用功能使用"
hiddenFromHomePage: false
hiddenFromSearch: false
featuredImage: "https://cdn5.maocdn.cn/img/2021/06/17/wp3082278-github-wallpapers.jpg"
featuredImagePreview: "https://cdn5.maocdn.cn/img/2021/06/17/wp3082255-github-wallpapers.jpg"
weight: 1
keywords: ["git", "git-usage","git rebase","git cherry-pick"]
tags: ["git", "git-usage","git rebase","git cherry-pick"]
categories: ["Git","Hunt"]
lightgallery: true
toc:
  enable: true
math:
  enable: false
showTags: true
license: ""
summary: "git使用常用的功能"
---

<!--more-->
## Git介绍
Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.
## Git常用命令
```
git pull
git push
git add
git commit
git rebase
git cherry-pick
git submodule
git lfs
```

## Git常用命令简述

#### git pull

#### git push

#### git add

#### git commit

#### git rebase

#### git cherry-pick

#### git submodule
#### git lfs
> git上传大文件
- 遇到的问题：一般git上传文件不会超过100M，当文件超过的时候会遇到下面问题
> remote: Resolving deltas: 100% (472/472), done.
> remote: error: GH001: Large files detected.
> You may want to try Git Large File Storage - https://git-lfs.github.com.

- 安装git-lfs 本机
    ```
    git lfs install
    ```
- 选择lfs管理的大文件(文件匹配支持通配符)
    ```
    git lfs track "the lage file's path"
    ```
- 添加.gitattributes文件
    ```
    git add .gitattributes
    ```
- git提交等操作
    ```
    git add xxx
    git commit -m "xxxx"
    git push origin main
    ```

## Git常见问题
#### `the remote end hung up unexpectedly`
**Resolve**
- 问题原因：推送文件太大
- 解决：修改设置git config文件的postBuffer的大小（500MB）
    -- git config --global http.postBuffer 524288000


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
categories: ["Git"]
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
```

## Git常用命令简述

#### git pull

#### git push

#### git add

#### git commit

#### git rebase

#### git cherry-pick

#### git submodule

## Git常见问题
#### `the remote end hung up unexpectedly`
**Resolve********
- 问题原因：推送文件太大
- 解决：修改设置git config文件的postBuffer的大小（500MB）
    -- git config --global http.postBuffer 524288000


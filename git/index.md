# Git常用功能(github)


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



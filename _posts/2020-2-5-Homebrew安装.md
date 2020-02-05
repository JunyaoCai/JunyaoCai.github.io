---
title: 'Homebrew安装'
date: 2020-2-5
permalink: /blog-posts/2020/2/5/Homebrew安装
tags:
  - distributed
  - machine learning
  - paper
---

Homebrew 安装过程

#### 1. 获取install文件

`curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install >> brew_install`

生成brew_install的文件在用户顶层文件夹下，与桌面/文档等文件夹并列

#### 2. 修改文件中的下载资源链接

这里采用中科大的镜像资源

`BREW_REPO = "git://mirrors.ustc.edu.cn/brew.git".freeze`

#### 3. 通过运行brew_install来安装

```
/usr/bin/ruby ~/brew_install
```

#### 4. 如果停在下面

```
==> Tapping homebrew/core
Cloning into '/usr/local/Homebrew/Library/Taps/homebrew/homebrew-core'...
```

进入`cd /usr/local/Homebrew/Library/Taps/homebrew`，复制 homebrew-core：`git clone https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-core.git`

#### 5. 把homebrew repo替换为[清华镜像](https://mirrors.tuna.tsinghua.edu.cn/help/homebrew)，并更新

```bash
//替换brew.git
$ cd "$(brew --repo)" 
$ git remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/brew.git

//替换homebrew-core.git
$ cd "$(brew --repo)/Library/Taps/homebrew/homebrew-core"
$ git remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-core.git

//替换Homebrew Bottles源，使用zsh的同学替换.bash_profile为.zshrc
$ echo 'export HOMEBREW_BOTTLE_DOMAIN=https://mirrors.tuna.tsinghua.edu.cn/homebrew-bottles' >> ~/.bash_profile
source ~/.bash_profile

//更新
$ brew update

可通过 $ brew config 查看brew的镜像更改信息
```








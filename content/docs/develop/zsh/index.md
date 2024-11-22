---
title: "安装配置zsh"
linkTitle: "zsh"
weight: 20
date: 2021-08-26
description: >
  安装配置zsh和ohmyzsh!
---

> 备注：先确保已经安装配置好 git 和 gitbash。

##  安装配置 zsh

### 下载zsh

Zsh下载地址：

https://packages.msys2.org/package/zsh?repo=msys&variant=x86_64

下载 .tar.zst 文件：

https://mirror.msys2.org/msys/x86_64/zsh-5.9-2-x86_64.pkg.tar.zst

这个文件可以用 windows11 自带的解压缩软件就能解压缩，得到 zsh-5.9-2-x86_64.pkg 目录，里面有两个子目录：etc 和 usr 。

### 安装zsh

复制 etc 和 usr 目录，粘贴到 git 的安装目录如 `D:\sky\work\soft\git` ，git 安装目录下同样有 etc 和 usr 目录，文件会自动合并进去。

### 运行zsh

运行时，要先启动 git 自带的 bash 终端，然后执行 zsh 命令，也可以查看 zsh 版本：

```bash
$ zsh --version
zsh 5.9 (x86_64-pc-msys)
```

为了方便使用，尤其是用 zsh 替代 bash，可以修改 bash 的配置文件 ~/.bashrc (如果没有就创建它) ，加入内容:

```bash
/c/Windows/System32/chcp.com 65001 > /dev/null 2>&1

if [ -t 1 ]; then
  exec zsh
fi
```

这样就可以自动 bash 时自动启动 zsh。

第一次执行 zsh 时会询问文件创建的问题，选择

```bash
Quit and do nothing.  The function will be run again next time.
```

### 安装 Oh my zsh!

在 zsh 终端执行:

```bash
# 如果被墙则增加代理设置
# export all_proxy=socks5://192.168.2.1:7891

sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

在这里下载并安装几个字体

https://github.com/romkatv/powerlevel10k#meslo-nerd-font-patched-for-powerlevel10k

- MesloLGS NF Regular.ttf
- MesloLGS NF Bold.ttf
- MesloLGS NF Italic.ttf
- MesloLGS NF Bold Italic.ttf

下载安装 Powerlevel10k 主题：

```bash
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```

修改

```bash
vi ~/.zshrc
```

增加内容:

```bash
ZSH_THEME="powerlevel10k/powerlevel10k"
POWERLEVEL9K_RIGHT_PROMPT_ELEMENTS=(history)
POWERLEVEL9K_SHORTEN_DIR_LENGTH=1

# User configuration
export LS_COLORS="rs=0:no=00:mi=00:mh=00:ln=01;36:or=01;31:di=01;34:ow=04;01;34:st=34:tw=04;34:pi=01;33:so=01;33:do=01;33:bd=01;33:cd=01;33:su=01;35:sg=01;35:ca=01;35:ex=01;32:"
```

安装 wd 插件：

```bash
sh -c "$(curl -fsSL https://github.com/mfaerevaag/wd/raw/master/install.sh)"
```

配置以下插件：

```bash
git clone https://github.com/zsh-users/zsh-autosuggestions.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
git clone https://github.com/zsh-users/zsh-history-substring-search.git $ZSH_CUSTOM/plugins/history-substring-search
git clone https://github.com/Pilaton/OhMyZsh-full-autoupdate.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/ohmyzsh-full-autoupdate
```

修改 zsh 配置

```bash
vi ~/.zshrc
```

注释掉这一行：

```bash
DISABLE_MAGIC_FUNCTIONS="true"
```

修改 plugins 为

```bash
plugins=(    
    git
    golang
    rust
    docker
    docker-compose 
    kubectl
    npm
    node
    mvn
    sudo
    helm
    redis-cli
    wd 
    zsh-autosuggestions
    zsh-syntax-highlighting
    history-substring-search
    ohmyzsh-full-autoupdate
)

# User configuration

ZSH_HIGHLIGHT_HIGHLIGHTERS=(main brackets pattern cursor root line)
ZSH_HIGHLIGHT_PATTERNS=('rm -rf *' 'fg=white,bold,bg=red')
```

重启 zsh。

```bash
Updating plugins and themes Oh My ZSH
--------------------------------------

Updating Plugin — ohmyzsh-full-autoupdate -> https://github.com/Pilaton/OhMyZsh-full-autoupdate
Already up to date.

Updating Plugin — zsh-autosuggestions -> https://github.com/zsh-users/zsh-autosuggestions
Already up to date.

Updating Plugin — zsh-syntax-highlighting -> https://github.com/zsh-users/zsh-syntax-highlighting
Already up to date.

Updating Theme — powerlevel10k -> https://github.com/romkatv/powerlevel10k
Already up to date.
```

备注： 这个自动更新可能会因为 github.com 被墙无法访问而失败。可以修改 .zshrc 的设置，默认开启代理避免更新时被墙：

```bash
# auto start proxy on
export all_proxy=socks5://192.168.2.1:7891;export http_proxy=http://192.168.2.1:7890;export https_proxy=http://192.168.2.1:7890;export no_proxy=127.0.0.1,localhost,local,.local,.lan,192.168.0.0/16,10.0.0.0/16
```

然后手工更新 ohmyzsh：

```bash
# proxyon
omz update
```

执行完 ohmyzsh 的更新之后，关闭所有的终端，再重新打开，就会触发 zsh plugins 的自动更新。

## 配置网络代理

修改 zsh 配置

```bash
vi ~/.zshrc
```

增加以下内容：

```bash
# proxy
alias proxyon='export all_proxy=socks5://192.168.2.1:7891;export http_proxy=http://192.168.2.1:7890;export https_proxy=http://192.168.2.1:7890;export no_proxy=127.0.0.1,localhost,local,.local,.lan,192.168.0.0/16,10.0.0.0/16'
alias proxyoff='unset all_proxy http_proxy https_proxy no_proxy'
```
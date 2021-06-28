# First Mac
 收录在 macOS 中使用体验绝佳的开源项目，如果你是第一次使用 macOS，那么这些项目一定必不可少！同时欢迎提交 PR 和建议。

## 优化命令

### 安全性与隐私-开启任何来源选项

```bash
sudo spctl --master-disable
```

## 优秀项目

### Homebrew

软件包管理器，完全基于 Git 和 Ruby。使用`brew cask`安装 macOS 应用程序、字体和插件以及其他非开源软件，会将软件包安装到独立目录，并将其文件软链接至 `/usr/local` 。

> 仓库地址：https://github.com/Homebrew
> 官网：https://brew.sh

安装命令：

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

普遍需要的一些库
```bash
brew tap homebrew/cask
brew tap homebrew/cask-versions
brew tap homebrew/cask-drivers
brew tap homebrew/cask-fonts
brew tap homebrew/services
brew tap buo/cask-upgrade
brew tap homebrew/bundle
```

### oh my zsh

让`zsh`复杂的配置降到`0`门槛，完全兼容`bash`。并提供了丰富的可选插件、主题。

> 仓库地址：https://github.com/ohmyzsh/ohmyzsh
> 官网：https://ohmyz.sh

安装命令：

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

常用插件：

```bash
# 命令语法高亮
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
# 历史记录建议
git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions

# 然后在配置文件中加入以上插件：
vim ~/.zshrc
# 编辑 plugins，将以上插件名称加入
plugins=( [plugins...] zsh-syntax-highlighting zsh-autosuggestions)
```



### Powerline Fonts

#### 普通全安装方式

`Vim statusline` 插件、字体集，支持很多特殊的`icon`字符。

> 仓库地址：https://github.com/powerline/fonts

安装命令：

```bash
# clone
git clone https://github.com/powerline/fonts.git --depth=1
# install
cd fonts
./install.sh
# clean-up a bit
cd ..
rm -rf fonts
```

#### 使用 Homebrew 

```bash
# 搜索 powerline 字体命令：
brew search powerline
# 选择性安装
brew install font-meslo-for-powerline
```

### Spaceship ZSH

提供了更加丰富的`ZSH`展现形式，并且与`Oh My Zsh`兼容。

> 仓库地址：https://github.com/denysdovhan/spaceship-prompt

安装命令：

```bash
# oh-my-zsh 环境下的安装

# Clone this repo:
git clone https://github.com/denysdovhan/spaceship-prompt.git "$ZSH_CUSTOM/themes/spaceship-prompt"
# Symlink spaceship.zsh-theme to your oh-my-zsh custom themes directory:
ln -s "$ZSH_CUSTOM/themes/spaceship-prompt/spaceship.zsh-theme" "$ZSH_CUSTOM/themes/spaceship.zsh-theme"
# And Set ZSH_THEME="spaceship" in your .zshrc.
```

由于 `Space­ship Prompt` 需要特殊的符号来显示开发环境版本信息，所以需要在终端工具里选择 `Pow­er­line Fonts` 字体 `Meslo LG` 系列中的一个，如 `"Meslo LG M for Powerline”`。

### Quick Look

> 仓库地址：https://github.com/sindresorhus/quick-look-plugins
>
> 目前可以使用 AppStore 中的`iPreview`代替

安装命令：

```bash
brew install qlcolorcode qlstephen qlmarkdown quicklook-json qlimagesize suspicious-package apparency quicklookase qlvideo
```

### neofetch

命令行系统信息工具。

> 仓库地址：https://github.com/dylanaraps/neofetch

安装命令：

```bash
# (homebrew)
brew install neofetch
```

![](img/4SPYFG.png)



## 其他

如果您需要升级您的 macOS 下的`zsh`版本，可按以下命令操作：

```bash
brew install zsh
# add shell path
sudo vim /etc/shells
# add the following line into the very end of the file(/etc/shells)
/usr/local/bin/zsh
# change default shell
chsh -s /usr/local/bin/zsh
# then you should to restart your computer
```

终端代理 `Alias`分享：

```bash
alias ss_proxy='export all_proxy=socks5://127.0.0.1:1086'
alias v2ray_proxy='export all_proxy=socks5://127.0.0.1:1081'
alias clashx_proxy='export https_proxy=http://127.0.0.1:7890 http_proxy=http://127.0.0.1:7890 all_proxy=socks5://127.0.0.1:7891'
alias un_proxy='unset all_proxy https_proxy http_proxy'
```

---

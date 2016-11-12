# mac下使用vim配置golang开发环境

## 依赖工具

* [macvim](https://github.com/macvim-dev/macvim/releases/tag/snapshot-114)

## 获取vim配置文件

``` bash
$ git clone --recursive https://github.com/LyricTian/vim.git $HOME/vim
$ ln -sf $HOME/vim/.vim $HOME/.vim
$ ln -sf $HOME/vim/.vimrc $HOME/.vimrc
```

## 安装插件

```
:PluginInstall
```

### 安装vim-go依赖包

```
# 安装依赖
:GoInstallBinaries
# 或更新依赖
:GoUpdateBinaries
```

### 编译YCM

``` bash
$ cd $HOME/.vim/bundle/YouCompleteMe
$ ./install.py --gocode-completer
```

### 安装ctags

``` bash
$ brew install ctags
```

### 配置`macvim`的环境变量

```
$ vim $HOME/.zprofile
```

```
export PATH="/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin"

export GOPATH="$HOME/go"
export GOROOT="/usr/local/go"
export PATH="$GOROOT/bin:$GOPATH/bin":$PATH

alias ctags="`brew --prefix`/bin/ctags"
```

## MIT License

```
Copyright (c) 2016 Lyric
```

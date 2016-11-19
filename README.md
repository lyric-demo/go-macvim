# vim配置golang开发环境

![screenshot](https://raw.githubusercontent.com/LyricTian/vim/master/screenshots/screenshot.png)

## 准备

### 安装依赖

- [Hack字体](https://github.com/chrissimpkins/Hack)
- [macvim](https://github.com/macvim-dev/macvim)
- `brew install cmake ctags`

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

## 配置

``` bash
$ git clone --recursive https://github.com/LyricTian/vim.git $HOME/vim
$ ln -sf $HOME/vim/.vim $HOME/.vim
$ ln -sf $HOME/vim/.vimrc $HOME/.vimrc
```

### 运行macvim

```
$ mvim
```

### 安装插件

```
:PluginInstall
```

### 安装vim-go依赖工具
> 更新工具使用`:GoUpdateBinaries`

```
:GoInstallBinaries
```

### 编译YCM
> 详细说明（[http://valloric.github.io/YouCompleteMe/](http://valloric.github.io/YouCompleteMe/)）

``` bash
$ cd $HOME/.vim/bundle/YouCompleteMe
$ ./install.py --gocode-completer
```

## 快捷键配置

```
" for tools
map <c-n><c-t> :NERDTreeToggle<cr>
map <c-t><c-t> :TagbarToggle<cr>


" for golang
autocmd FileType go noremap <buffer> <c-g><c-t> :TagbarToggle<cr>
autocmd FileType go noremap <buffer> <c-g><c-b> :GoBuild<cr>
autocmd FileType go noremap <buffer> <c-g><c-h> :GoDoc<cr>
autocmd FileType go noremap <buffer> <c-g><c-p> :GoDefPop<cr>
autocmd FileType go noremap <buffer> <c-g><c-d> :GoDef<cr>
autocmd FileType go noremap <buffer> <c-g><c-i> :GoImports<cr>
autocmd FileType go noremap <buffer> <c-g><c-r> :GoReferrers<cr>

" for javascript
autocmd FileType javascript noremap <buffer>  <c-j><c-f> :call JsBeautify()<cr>

" for json
autocmd FileType json noremap <buffer> <c-j><c-f> :call JsonBeautify()<cr>

" for jsx
autocmd FileType jsx noremap <buffer> <c-j><c-f> :call JsxBeautify()<cr>

" for html
autocmd FileType html noremap <buffer> <c-j><c-f> :call HtmlBeautify()<cr>

" for css or scss
autocmd FileType css noremap <buffer> <c-j><c-f> :call CSSBeautify()<cr>

```

## MIT License

```
Copyright (c) 2016 Lyric
```

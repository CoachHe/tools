# 1. 安装插件支持
在shell中执行
```shell
curl -fLo ~/.vim/autoload/plug.vim --create-dirs \ https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```
# 2. 安装Vundle插件支持
## 安装Vundle:
```shell
git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
~/.vimrc
```
## 文件中也添加如下命令：
```shell
set nocompatible
filetype off
set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()
Plugin 'VundleVim/Vundle.vim'
```
 
## Plugs下面加入你需要的vim-plug
```shell
Plugin 'vim-airline/vim-airline'
call vundle#end()
filetype plugin indent on
```
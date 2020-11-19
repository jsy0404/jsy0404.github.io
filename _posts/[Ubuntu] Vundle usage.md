# [Ubuntu] Vundle usage

```shell
git clone https://github.com/VundleVim/Vundle.vim.git
mv Vundle.vim ~/.vim/bundle/Vundle.vim
```
## .vimrc
```
set nocompatible
filetype off
set rtp+=~/.vim/bundle/Vundle.vim
call vundle#rc('~/.vim/bundle')
call vundle#begin()
Plugin 'DoxygenToolkit.vim'
call vundle#end()
filetype plugin indent on
map <f10> :Dox<cr>
```

# vimrc setting

```shell
#update vim
sudo add-apt-repository ppa:jonathonf/vim
sudo apt update
sudo apt install vim
```

```shell
sudo apt update
sudo apt install -y build-essential cmake
mkdir -p ~/.vim/colors
cd ~/.vim/colors
curl -O https://raw.githubusercontent.com/nanotech/jellybeans.vim/master/colors/jellybeans.vim
cp jellybeans.vim /usr/share/vim/vim81/colors/
git clone https://github.com/Valloric/YouCompleteMe ~/.vim/bundle/YouCompleteMe
cd ~/.vim/bundle/YouCompleteMe
git submodule update --init --recursive
~/.vim/bundle/YouCompleteMe/install.py
git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
cd
vim .vimrc
```

```
nnoremap j jzz 

nnoremap <S-G> <S-G><End>

nnoremap tt :tabnew .<Enter>
nnoremap <C-Tab> gT
nnoremap <Tab> gt
nnoremap <A-Right> gt
nnoremap <A-Left> gT

set nu  

nnoremap \ :YcmCompleter GoTo<CR>
nnoremap <C-\> <C-O>
set nocompatible
filetype off
set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()
Plugin 'VundleVim/Vundle.vim'
Plugin 'Valloric/YouCompleteMe'
```



```shell
set hlsearch
set nu
set autoindent
set scrolloff=2
set wildmode=longest,list
set ts=4
set sts=4
set sw=1
set autowrite
set autoread
set cindent
set bs=eol,start,indent
set history=256
set laststatus=2
set paste
set shiftwidth=4
set showmatch
set smartcase
set smarttab
set smartindent
set softtabstop=4
set tabstop=4
set ruler
set incsearch
set statusline=\ %<%l:%v\ [%P]%=%a\ %h%m%r\ %F\
au BufReadPost *
\ if line("'\"") > 0 && line("'\"") <= line("$") |
\ exe "norm g`\"" |
\ endif
if $LANG[0]=='k' && $LANG[1]=='o'
set fileencoding=korea
endif
if has("syntax")
 syntax on
endif
colorscheme jellybeans
```


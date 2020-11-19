# Cscope Ctags usage

## Install ctags cscope

```shell
sudo apt install ctags cscope
```

## Create tags, cscope.out

```shell
ctags -R
cscope -R
```

## .vimrc settings

```shell
set tags=./tags
set csprg=/usr/bin/cscope
set csto=0
set cst
set nocsverb

if filereadable("./cscope.out")
cs add cscope.out
else
cs add /usr/src/linux/cscope.out
endif
set csverb
```


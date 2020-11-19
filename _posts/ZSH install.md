# ZSH install

## ZSH isntall

```shell
sudo apt install zsh #zsh install
chsh -s /usr/bin/zsh #Change current shell to zsh
sudo reboot
```

## Oh-my-zsh install

```shell
sudo apt install curl
sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ~/powerlevel10k #Use powerlevel10k theme
echo 'source ~/powerlevel10k/powerlevel10k.zsh-theme' >>! ~/.zshrc #Copy powerlevel10k to .zshrc
source ~/.zshrc
```
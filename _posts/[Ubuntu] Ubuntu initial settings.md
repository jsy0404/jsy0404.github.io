# [Ubuntu] Ubuntu initial settings

## Basic module

```shell
sudo apt update
sudo apt install python3-pip #pip install
sudo apt install vim #Vim install
sudo apt install git #git install
sudo apt install openssh-server #ssh install
sudo apt install ctags cscope
sudo apt install tmux
```

## GUI Desktop

### Chrome Install

```shell
wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | sudo apt-key add -
sudo sh -c 'echo "deb [arch=amd64] http://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google.list'
sudo apt update
sudo apt install google-chrome-stable
sudo rm -rf /etc/apt/sources.list.d/google.list
```

### Typora Install

```shell
wget -qO - https://typora.io/linux/public-key.asc | sudo apt-key add -
sudo add-apt-repository 'deb https://typora.io/linux ./'
sudo apt update
sudo apt install typora
```


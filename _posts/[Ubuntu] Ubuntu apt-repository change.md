# [Ubuntu] Ubuntu apt-repository change

```shell
sudo vi /etc/apt/source.list
:%s/kr.archive.ubuntu.com/mirror.kakao.com
sudo apt update
```


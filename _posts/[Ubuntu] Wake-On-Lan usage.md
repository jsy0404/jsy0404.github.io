# [Ubuntu] Wake-On-Lan usage

```shell
sudo apt-get install net-tools ethtool wakeonlan
sudo ethtool -s enp37s0 wol g # enp37s0 == network driver
sudo ethtool enp37s0 # enp37s0 == network driver
sudo vi /etc/network/interfaces
```

```shell
post-up /sbin/ethtool -s enp37s0 wol g # enp37s0 == network driver
post-down /sbin/ethtool -s enp37s0 wol g # enp37s0 == network driver
```


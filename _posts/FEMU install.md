# FEMU install

```shell
git clone https://github.com/ucare-uchicago/femu.git
cd femu
mkdir build-femu
cd build-femu
cp ../femu-scripts/femu-copy-scripts.sh .
./femu-copy-scripts.sh .
sudo ./pkgdep.sh
./femu-compile.sh
```

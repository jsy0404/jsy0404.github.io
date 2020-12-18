# RocksDB usage

```shell
sudo apt-get install openjdk-11-jre
sudo apt-get install openjdk-11-jdk
sudo apt install libsnappy-dev
sudo apt install maven
```

```shell
#Edit /etc/profile
export JAVA_HOME=$(dirname $(dirname $(readlink -f $(which java))))
```

```shell
source /etc/profile
sudo apt install g++
git clone https://github.com/facebook/rocksdb.git
cd rocksdb
```
```shell
# Edit Makefile
# A version of each $(LIBOBJECTS) compiled with -fPIC and a fixed set of static compression libraries
java_static_libobjects = $(patsubst %,jls/%,$(LIBOBJECTS))
CLEAN_FILES += jls

ifneq ($(ROCKSDB_JAVA_NO_COMPRESSION), 1)
# JAVA_COMPRESSIONS = libz.a libbz2.a libsnappy.a liblz4.a libzstd.a
JAVA_COMPRESSIONS = libsnappy.a
endif

# JAVA_STATIC_FLAGS = -DZLIB -DBZIP2 -DSNAPPY -DLZ4 -DZSTD
JAVA_STATIC_FLAGS = -DSNAPPY
# JAVA_STATIC_INCLUDES = -I./zlib-$(ZLIB_VER) -I./bzip2-$(BZIP2_VER) -I./snappy-$(SNAPPY_VER) -I./lz4-$(LZ4_VER)/lib -I./ zstd-$(ZSTD_VER)/lib
JAVA_STATIC_INCLUDES = -I./snappy-$(SNAPPY_VER)

rocksdbjavastaticrelease: rocksdbjavastatic
  # cd java/crossbuild && vagrant destroy -f && vagrant up linux32 && vagrant halt linux32 && vagrant up linux64 && vagrant halt linux64
  cd java;jar -cf target/$(ROCKSDB_JAR_ALL) HISTORY*.md
  # cd java/target;jar -uf $(ROCKSDB_JAR_ALL) librocksdbjni-*.so librocksdbjni-*.jnilib
  cd java/target;jar -uf $(ROCKSDB_JAR_ALL) librocksdbjni-*.so
  cd java/target/classes;jar -uf ../$(ROCKSDB_JAR_ALL) org/rocksdb/*.class org/rocksdb/util/*.class
```

```shell
make rocksdbjavastaticrelease -j32
```

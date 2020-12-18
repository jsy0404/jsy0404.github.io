# YCSB usage

```shell
git clone https://github.com/brianfrankcooper/YCSB.git
cd YCSB
git checkout 0.15.0
```

```shell
# Add YCSB/rocksdb/pom.xml
<dependency>
      <groupId>org.apache.htrace</groupId>
      <artifactId>htrace-core4</artifactId>
      <version>4.1.0-incubating</version>
</dependency>
<dependency>
      <groupId>org.hdrhistogram</groupId>
      <artifactId>HdrHistogram</artifactId>
      <version>2.1.4</version>
</dependency>
```

```shell
mvn -pl com.yahoo.ycsb:rocksdb-binding -am clean package
```

```shell
# ./load.sh
bin/ycsb.sh load rocksdb -s -P workloads/workloada -p rocksdb.dir=/mnt/nvme/rocksdb
```

```shell
# ./run.sh
bin/ycsb.sh run rocksdb -s -P workloads/workloada -p rocksdb.dir=/mnt/nvme/rocksdb
```

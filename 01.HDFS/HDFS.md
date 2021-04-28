# HDFS

`hadoop fs -touchz /tmp/smok_test.txt

echo "hello world" | hdfs dfs -appendToFile - /tmp/smok_test.txt

hdfs dfs -cat /tmp/smok_test.txt

su hdfs

hdfs dfs -rmr /tmp/smok_test.txt`


```bash
# Replace $ZOOKEEPER 'localhost' with the correct hostname.
# Multiple ZooKeepers can be specified with commas: 'host1:2181,host2:2181,host3:2181'
ZOOKEEPER=localhost:2181

cat <<EOF >/tmp/zk.$$
create /zk_test my_data
ls /
get /zk_test
set /zk_test junk
get /zk_test
quit
EOF

cat /tmp/zk.$$ | zookeeper-client -server $ZOOKEEPER
```
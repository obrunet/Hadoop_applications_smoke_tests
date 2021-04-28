# HDFS

```bash
`hadoop fs -touchz /tmp/smok_test.txt

echo "hello world" | hdfs dfs -appendToFile - /tmp/smok_test.txt

hdfs dfs -cat /tmp/smok_test.txt

su hdfs

hdfs dfs -rmr /tmp/smok_test.txt`
```
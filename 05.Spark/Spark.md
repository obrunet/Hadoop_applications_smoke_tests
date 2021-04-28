# Spark


## Spark alone
```bash
su hdfs
/usr/bin/spark3-shell
```

or
```bash
/opt/cloudera/parcels/SPARK3/bin/spark3-submit \
               --class org.apache.spark.examples.SparkPi \
               --master yarn \
               --deploy-mode cluster \
               --num-executors 1 \
               --executor-memory 1g \
               --driver-memory 1g \
               --executor-cores 1 \
               /opt/cloudera/parcels/SPARK3/lib/spark3/examples/jars/spark-examples*.jar 10
```
mode cluster or client
same thing for v3


## Spark with HDFS
```bash
hdfs dfs -put /tmp/smoke_tests.csv /tmp/smoke_tests.csv

/opt/cloudera/parcels/CDH/bin/spark-submit
    --master yarn
    --deploy-mode client
    --num-executors 1
    --executor-memory 1g
    --driver-memory 1g
    --executor-cores 1
    /tmp/smoke_tests_spark_hdfs.py

hdfs dfs -ls /tmp/test_changed.csv | wc -l
```
details of the file

```python
# import all needed libs
from pyspark.sql import SparkSession
from pyspark.sql.functions import *
 

# create a session
sparkSession = SparkSession.builder.appName("pyspark_test").getOrCreate()


# read a file from HDFS
df = sparkSession.read.option("header",True).option("inferSchema", True).csv("hdfs:///tmp/smoke_tests.csv")
df.show()


# write a file to HDFS
df2 = df.withColumn('NAME', upper(col('name'))) \
    .withColumn('station_id', col("station_id") + 1000) \
    .withColumn('Constant', lit(1000)) \
    .withColumn("result", col("station_id") + col("dockcount") - 10000).drop(col("landmark"))

df2.show()
df2.coalesce(2).write.csv("hdfs:///tmp/test_changed.csv")
```b

## Spark with hive
```bash
/opt/cloudera/parcels/CDH/lib/spark/bin/spark-submit /home/app_admin/spark-hive.py
```

file :

```python 
from os.path import abspath
from pyspark.sql import SparkSession
from pyspark.sql import Row


warehouse_location = abspath('spark-warehouse')

spark = SparkSession \
    .builder \
    .appName("Python Spark SQL Hive Smoke Test") \
    .config("spark.sql.warehouse.dir", warehouse_location) \
    .enableHiveSupport() \
    .getOrCreate()

spark.sql("CREATE TABLE IF NOT EXISTS smoke_test_hive(name VARCHAR(64), age INT)")
spark.sql("INSERT INTO smoke_test_hive VALUES ('Salem ',30),('Olivier',30)")

# Simple query
spark.sql("SELECT * FROM smoke_test_hive").show()

# Aggregation query
spark.sql("SELECT COUNT(*) FROM smoke_test_hive").show()

# Drop Table query
spark.sql("DROP TABLE IF EXISTS smoke_test_hive")
```
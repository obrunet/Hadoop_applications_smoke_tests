# Hadoop Smoke Tests

This repository contains scripts or commands to run compact, __simple applications__ that will __test the basic functionality__ of the various components of a Hadoop cluster. 

These basic code snippets should work on all known distributions : Hortonworks HDP & HDF , MapR, but where especially developed / crafted for __[Cloudera CDP (private cloud 7.1.3)](https://www.cloudera.com/products/cloudera-data-platform.html)__

One might use these when setting up a new cluster or after a cluster upgrade to prove that the services work.

## Guidelines
- When possible, __Create, read, update, and delete (CRUD)__ functions are implemented.
- Tests can be performed __from the Edge/Gateway__ node __or__ from __slaves / masters__ depending on the cases. For example, you can submit spark jobs in cluster or client mode.
- __No additional software should be needed__ to run the test, but a minimal configuration for each component should be done before.
- Unit testing is performed first. Then two components are tested to see if they are able to communicate, for instance spark operations on hdfs
- Results are checked to determine if a specific test passed or failed.
- Lanugages used: __shell__, __SQL__, __python__ and __scala__


## Table of Contents
01. [HDFS](https://github.com/obrunet/Hadoop_applications_smoke_tests/tree/main/01.HDFS/HDFS.md)
02. [Hive](https://github.com/obrunet/Hadoop_applications_smoke_tests/tree/main/02.Hive/Hive.md)
03. [Hbase](https://github.com/obrunet/Hadoop_applications_smoke_tests/tree/main/03.Hbase/Hbase.md)
04. [MapReduce](https://github.com/obrunet/Hadoop_applications_smoke_tests/tree/main/04.MapReduce/MapReduce.md)
05. [Spark 2 & 3 (with HDFS, Hive & Hbase)](https://github.com/obrunet/Hadoop_applications_smoke_tests/tree/main/05.Spark/Spark.md)
06. [Phoenix](https://github.com/obrunet/Hadoop_applications_smoke_tests/tree/main/06.Phoenix/Phoenix.md)
07. [Pig](https://github.com/obrunet/Hadoop_applications_smoke_tests/tree/main/07.HDFS/HDFS.md)
08. [SolR](https://github.com/obrunet/Hadoop_applications_smoke_tests/tree/main/08.Pig/Pig.md)
09. [Oozie](https://github.com/obrunet/Hadoop_applications_smoke_tests/tree/main/09.Oozie/Oozie.md)
10. [Sqoop](https://github.com/obrunet/Hadoop_applications_smoke_tests/tree/main/10.Sqoop/Sqoop.md)
11. [Flume](https://github.com/obrunet/Hadoop_applications_smoke_tests/tree/main/11.Flume/Flume.md)
12. [Kafka](https://github.com/obrunet/Hadoop_applications_smoke_tests/tree/main/12.Kafka/Kafka.md)
13. [Various scripts](https://github.com/obrunet/Hadoop_applications_smoke_tests/tree/main/13.Misc/Misc.md)


Please see [CONTRIBUTING.md]() for information on how to contribute.

## License
__Copyleft__, since this is an aggregation of ressources freely available on the internet / docs of each components.

## Other ressources & references
- [teamclairvoyant - hadoop-smoke-tests](https://github.com/teamclairvoyant/hadoop-smoke-tests)
- [godatadriven - hdp-smokey](https://github.com/godatadriven/hdp-smokey)
- [zmousa - hadoop-smoke-test](https://github.com/zmousa/hadoop-smoke-test)
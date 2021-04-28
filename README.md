# Hadoop Smoke Tests

This repository contains scripts or commands to run compact, __simple applications__ that will __test the basic functionality__ of the various components of a Hadoop cluster. 

These basic code snippets should work on all known distributions : Hortonworks HDP , MapR, but where especially developed / crafted for __[Cloudera CDP (private cloud 7.1.3)](https://www.cloudera.com/products/cloudera-data-platform.html)__

One might use these when setting up a new cluster or after a cluster upgrade to prove that the services work.

## Guidelines
- When possible, __Create, read, update, and delete (CRUD)__ functions are done.
- Tests can be performed __from the Edge/Gateway__ node __or__ from __slaves / masters__ depending on the cases. For example, you can submit spark jobs in cluster or client mode.
- __No additional software should be needed__ to run the test, but a minimal configuration for each component should be done before.
- Unit testing is performed first. Then two components are tested to see if they are able to communicate, for instance spark operations on hdfs
- Results are checked to determine if a specific test passed or failed.
- Lanugages used: __shell__, __SQL__, __python__ and __scala__


## Example
Can I get a directory listing from HDFS?
Can I write a file to HDFS?
Can I read that file back from HDFS?

ffffffffffffffffffff

Please see [CONTRIBUTING.md]() for information on how to contribute.

## License
__Copyleft__, since this is an aggregation of ressources freely available on the internet / docs of each components.

## Other ressources & references
- [teamclairvoyant - hadoop-smoke-tests](https://github.com/teamclairvoyant/hadoop-smoke-tests)
- [godatadriven - hdp-smokey](https://github.com/godatadriven/hdp-smokey)
- [zmousa - hadoop-smoke-test](https://github.com/zmousa/hadoop-smoke-test)
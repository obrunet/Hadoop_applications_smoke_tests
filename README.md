# Hadoop Smoke Tests

This repository containes documents that describe how to run compact, simple, cut and paste code that will test the basic functionality of the various components of a Hadoop cluster. One might use these when setting up a new cluster or after a cluster upgrade to prove that the services work.

## Guidelines
- When possible, Create, read, update, and delete (CRUD) functions are done.
- Tests can be performed from the Edge/Gateway node or from slaves / masters. For example, you can submit spark jobs in cluster or client mode.
- No additional software should be needed to run the test, but a minimal configuration for each component should be done before.
- Unit testing is performed first, then two components are tested to see if they are able to communicate, for instance spark operations on hdfs
- Results are checked to determine if the test passed or failed.


## Example
Can I get a directory listing from HDFS?
Can I write a file to HDFS?
Can I read that file back from HDFS?
Contributing
Please see CONTRIBUTING.md for information on how to contribute.

## License
Copyleft, since this is an aggregation of ressources freely available on docs of each components.

## Other ressources & sources

- [teamclairvoyant - hadoop-smoke-tests](https://github.com/teamclairvoyant/hadoop-smoke-tests)
- [godatadriven - hdp-smokey](https://github.com/godatadriven/hdp-smokey)
- [zmousa - hadoop-smoke-test](https://github.com/zmousa/hadoop-smoke-test)
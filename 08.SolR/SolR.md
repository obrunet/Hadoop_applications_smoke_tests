# SolR

```bash
# SOLR Smoke tests - commands summary
# Web UI with a graph : http://XX.XX.XX.XX:8983/solr/#/~cloud?view=graph


# generate an instance dir
solrctl instancedir --generate /tmp/solr.$$
# return : nothing

# create a specific conf
solrctl instancedir --create smoke_tests_config /tmp/solr.$$
# return :  Uploading configs from

# list all confs
solrctl instancedir --list
# return :  smoke_tests_config

# create a collection with 2 shards, the previous conf & 1 replica
solrctl collection --create smoke_tests_collection -s 2 -c smoke_tests_config -r 1
# return :  nothing

# list all collections
solrctl collection --list
# return :  smoke_tests_collection

# index several xml files in the collection
java -Durl=http://$HOSTNAME:8983/solr/smoke_tests_collection/update \
               -jar /opt/cloudera/parcels/CDH/share/doc/solr-doc*/example/exampledocs/post.jar \
               /opt/cloudera/parcels/CDH/share/doc/solr-doc*/example/exampledocs/*.xml
# return :  files indexed.

# get some stats
solrctl collection --stat smoke_tests_collection
# return : smoke_tests_collection/leader_elect

# search for a specific string TWINX2048-3200PRO in the collection
curl "http://$HOSTNAME:8983/solr/smoke_tests_collection/select?q=id:TWINX2048-3200PRO"
# return :  "response":{"numFound":1,"start":0,"maxScore":1.0466295,"docs":[

# delete the collection
solrctl collection  --delete smoke_tests_collection

#not working : solrctl instancedir --delete /tmp/solr.$$
#instead of HOSTNAME you can use : ${SOLRSERVER}
```
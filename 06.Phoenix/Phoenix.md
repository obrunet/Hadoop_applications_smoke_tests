# Phoenix

```bash
/opt/cloudera/parcels/CDH/lib/phoenix/bin/psql.py \
    groups['master_servers'][0]:2181:/hbase /opt/cloudera/parcels/CDH/lib/phoenix/doc/examples/WEB_STAT.sql \
    /opt/cloudera/parcels/CDH/lib/phoenix/doc/examples/WEB_STAT.csv \
    /opt/cloudera/parcels/CDH/lib/phoenix/doc/examples/WEB_STAT_QUERIES.sql
```
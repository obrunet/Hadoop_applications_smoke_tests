# Hive

Create the following file "hive_smoke_test.sql":
```sql
CREATE temporary TABLE smoke_test_hive (name VARCHAR(64), age INT)

CLUSTERED BY (age) INTO 2 BUCKETS STORED AS ORC;

INSERT INTO smoke_test_hive

  VALUES ('NameUser_1 ',31),('NameUser_2 ',18);

SELECT count(*) from smoke_test_hive ;
```
 

Then replace le variable master_servers by the corresponding IP & the specific port :

```bash
beeline -u jdbc:hive2://{{ groups['master_servers'][0] }}:{{ hive_port}} -f /home/chemin/hive_smoke_test.sq
```
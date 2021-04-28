# Pig

add impala to TOC

# Impala

```sql
-- IMPALA smoke tests CRUD (Create Read Update Delete)
-- su hdfs
-- impala-shell --query_file /tmp/smoke_tests_impala.sql
-- more infos on commands : https://www.tutorialspoint.com/impala/impala_shell.htm
-- create a database

CREATE DATABASE IF NOT EXISTS smoke_db;
SHOW databases;
USE smoke_db;

CREATE TABLE IF NOT EXISTS smoke_db.smoke_table (Id INT, name STRING, age INT, address STRING, salary BIGINT);

SHOW tables;

-- create records in the table
INSERT INTO smoke_table (ID, NAME, AGE, ADDRESS, SALARY) VALUES (1, 'Thierry', 44, 'Cameroon', 2000000 );
INSERT INTO smoke_table VALUES (2, 'Frederic', 34, 'Courbevoie', 10000 );
INSERT INTO smoke_table VALUES (3, 'Mohamed', 18, 'Casa', 15000 );

-- read records
SELECT * FROM smoke_table;

-- update records
INSERT OVERWRITE smoke_table VALUES (1, 'Cristian', 40, 'Anywhere', 2000000);
INSERT INTO smoke_table VALUES (6, 'Walid', 20, 'Paris', 10600);
INSERT INTO smoke_table VALUES (2, 'Frederic', 34, 'Courbevoie', 10000 );
INSERT INTO smoke_table VALUES (3, 'Mohamed', 18, 'Casa', 15000 );

-- read records
SELECT * FROM smoke_table;
SELECT * FROM smoke_table WHERE salary < 2000000 ORDER BY salary DESC LIMIT 2;

-- delete the table then the db
DROP TABLE smoke_db.smoke_table;
USE default;
DROP DATABASE IF EXISTS smoke_db;
```
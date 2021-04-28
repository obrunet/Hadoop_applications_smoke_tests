# Hbase


Apache HBase is an open source, non-relational, distributed database modeled after Google's BigTable and is written in Java. It is developed as part of Apache Software Foundation's Apache Hadoop project and runs on top of HDFS (Hadoop Distributed File System), providing BigTable-like capabilities for Hadoop. That is, it provides a fault-tolerant way of storing large quantities of sparse data (small amounts of information caught within a large collection of empty or unimportant data, such as finding the 50 largest items in a group of 2 billion records, or finding the non-zero items representing less than 0.1% of a huge collection).

http://hbase.praveendeshmane.co.in/hbase/hbase-CRUD-operations.jsp

https://www.tutorialspoint.com/hbase/hbase_shell.htm

 
```bash
su hbase
/usr/bin/hbase shell
 
# creating table
create 'emp','personal data','professional data'

# inserting data into table
put 'emp','1','personal data:name','raju'
put 'emp','1','personal data:city','hyderabad'
put 'emp','1','professional data:designation','manager'
put 'emp','1','professional data:salary','50000'
put 'emp','1','personal data:name','raju'; put 'emp','1','personal data:city','hyderabad'; put 'emp','1','professional data:designation','manager'; put 'emp','1','professional data:salary','50000'

# view or Scan
scan 'emp'

# Update
put 'emp','1','personal data:city','Delhi'

# Verify or Scan
scan 'emp'

# Retrieve
get 'emp', '1'
get 'emp', '1', {COLUMN=>'personal data:name'}

# Delete
delete 'emp', '1', 'personal data:city'
deleteall 'emp','1'

# View or Scan
scan 'emp'

# Count and Truncate
count 'emp'
truncate 'emp'
scan 'emp'
 
# Grant, revoke and list all permissions
grant 'praveen', 'RWXCA'
revoke 'praveen'
user_permission 'emp'
```bash
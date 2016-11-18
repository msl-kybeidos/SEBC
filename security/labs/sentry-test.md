```
[msl-kybeidos@ip-172-31-11-226 /]$ beeline
Beeline version 1.1.0-cdh5.8.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-11-226.eu-central-1.compute.internal@MSL-KYBEIDOS.COM
scan complete in 5ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-11-226.eu-central-1.compute.internal@MSL-KYBEIDOS.COM
Enter username for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-11-226.eu-central-1.compute.internal@MSL-KYBEIDOS.COM: msl-kybeidos
Enter password for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-11-226.eu-central-1.compute.internal@MSL-KYBEIDOS.COM: ********
Connected to: Apache Hive (version 1.1.0-cdh5.8.3)
Driver: Hive JDBC (version 1.1.0-cdh5.8.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20161118023838_c6c04646-f565-49c6-a723-b3c0e4698639): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20161118023838_c6c04646-f565-49c6-a723-b3c0e4698639); Time taken: 0.904 seconds
INFO  : Executing command(queryId=hive_20161118023838_c6c04646-f565-49c6-a723-b3c0e4698639): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20161118023838_c6c04646-f565-49c6-a723-b3c0e4698639); Time taken: 0.568 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+
No rows selected (2.832 seconds)
```
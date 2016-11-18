* Verify user privileges
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
* Create a Sentry role with full authorization
```
0: jdbc:hive2://localhost:10000/default> create role sentry_admin;
INFO  : Compiling command(queryId=hive_20161118024040_7d0e77e0-f799-4932-8c4a-83444b2a82b4): create role sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20161118024040_7d0e77e0-f799-4932-8c4a-83444b2a82b4); Time taken: 0.092 seconds
INFO  : Executing command(queryId=hive_20161118024040_7d0e77e0-f799-4932-8c4a-83444b2a82b4): create role sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20161118024040_7d0e77e0-f799-4932-8c4a-83444b2a82b4); Time taken: 0.864 seconds
INFO  : OK
No rows affected (0.97 seconds)
0: jdbc:hive2://localhost:10000/default> grant all on server server1 to role sentry_admin;
INFO  : Compiling command(queryId=hive_20161118024141_47674dad-76ad-4352-9d9c-6506ebdf13d3): grant all on server server1 to role sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20161118024141_47674dad-76ad-4352-9d9c-6506ebdf13d3); Time taken: 0.091 seconds
INFO  : Executing command(queryId=hive_20161118024141_47674dad-76ad-4352-9d9c-6506ebdf13d3): grant all on server server1 to role sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20161118024141_47674dad-76ad-4352-9d9c-6506ebdf13d3); Time taken: 0.096 seconds
INFO  : OK
No rows affected (0.197 seconds)
0: jdbc:hive2://localhost:10000/default> grant role sentry_admin to group `msl-kybeidos`;
INFO  : Compiling command(queryId=hive_20161118025050_497fced5-ff55-419b-b09c-3755472fa68a): grant role sentry_admin to group `msl-kybeidos`
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20161118025050_497fced5-ff55-419b-b09c-3755472fa68a); Time taken: 0.083 seconds
INFO  : Executing command(queryId=hive_20161118025050_497fced5-ff55-419b-b09c-3755472fa68a): grant role sentry_admin to group `msl-kybeidos`
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20161118025050_497fced5-ff55-419b-b09c-3755472fa68a); Time taken: 0.116 seconds
INFO  : OK
No rows affected (0.265 seconds)
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20161118025050_df130b31-f468-424f-b721-6a538354e363): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20161118025050_df130b31-f468-424f-b721-6a538354e363); Time taken: 0.073 seconds
INFO  : Executing command(queryId=hive_20161118025050_df130b31-f468-424f-b721-6a538354e363): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20161118025050_df130b31-f468-424f-b721-6a538354e363); Time taken: 0.151 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.321 seconds)
```
* Create additional test users
```
[root@ip-172-31-11-226 ~]# groupadd -g 1100 selector
[root@ip-172-31-11-226 ~]# groupadd -g 1200 inserters
[root@ip-172-31-11-226 ~]# simsh groupadd -g 1100 selector
Node4: no output
Node1: no output
Node2: no output
Node3: no output
[root@ip-172-31-11-226 ~]# simsh groupadd -g 1200 inserters
Node4: no output
Node1: no output
Node2: no output
Node3: no output
[root@ip-172-31-11-226 ~]# useradd -u 1100 --gid 1100 george
[root@ip-172-31-11-226 ~]# useradd -u 1200 --gid 1200 ferdinand
[root@ip-172-31-11-226 ~]# simsh useradd -u 1100 --gid 1100 george
Node1: no output
Node4: no output
Node3: no output
Node2: no output
[root@ip-172-31-11-226 ~]# simsh useradd -u 1200 --gid 1200 ferdinand
Node1: no output
Node4: no output
Node2: no output
Node3: no output
[root@ip-172-31-11-226 ~]# kadmin.local
Authenticating as principal root/admin@MSL-KYBEIDOS.COM with password.
kadmin.local:  add_principal george
WARNING: no policy specified for george@MSL-KYBEIDOS.COM; defaulting to no policy
Enter password for principal "george@MSL-KYBEIDOS.COM":
Re-enter password for principal "george@MSL-KYBEIDOS.COM":
Principal "george@MSL-KYBEIDOS.COM" created.
kadmin.local:  add_principal ferdinand
WARNING: no policy specified for ferdinand@MSL-KYBEIDOS.COM; defaulting to no policy
Enter password for principal "ferdinand@MSL-KYBEIDOS.COM":
Re-enter password for principal "ferdinand@MSL-KYBEIDOS.COM":
Principal "ferdinand@MSL-KYBEIDOS.COM" created.
```
* Create Test roles
```
[msl-kybeidos@ip-172-31-11-226 root]$ beeline
Beeline version 1.1.0-cdh5.8.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-11-226.eu-central-1.compute.internal@MSL-KYBEIDOS.COM
scan complete in 3ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-11-226.eu-central-1.compute.internal@MSL-KYBEIDOS.COM
Enter username for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-11-226.eu-central-1.compute.internal@MSL-KYBEIDOS.COM: msl-kybeidos
Enter password for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-11-226.eu-central-1.compute.internal@MSL-KYBEIDOS.COM: ********
Connected to: Apache Hive (version 1.1.0-cdh5.8.3)
Driver: Hive JDBC (version 1.1.0-cdh5.8.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> create role reads;
INFO  : Compiling command(queryId=hive_20161118025858_636606bc-0660-473c-b98f-8a3bc1aa092b): create role reads
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20161118025858_636606bc-0660-473c-b98f-8a3bc1aa092b); Time taken: 0.067 seconds
INFO  : Executing command(queryId=hive_20161118025858_636606bc-0660-473c-b98f-8a3bc1aa092b): create role reads
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20161118025858_636606bc-0660-473c-b98f-8a3bc1aa092b); Time taken: 0.041 seconds
INFO  : OK
No rows affected (0.166 seconds)
0: jdbc:hive2://localhost:10000/default> create role writes;
INFO  : Compiling command(queryId=hive_20161118025858_1a90e9c0-aa14-4145-8548-e25b56aa945d): create role writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20161118025858_1a90e9c0-aa14-4145-8548-e25b56aa945d); Time taken: 0.059 seconds
INFO  : Executing command(queryId=hive_20161118025858_1a90e9c0-aa14-4145-8548-e25b56aa945d): create role writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20161118025858_1a90e9c0-aa14-4145-8548-e25b56aa945d); Time taken: 0.031 seconds
INFO  : OK
No rows affected (0.099 seconds)
```
* Grant read privilege for all tables to read
```
0: jdbc:hive2://localhost:10000/default> grant select on database default to role reads;
INFO  : Compiling command(queryId=hive_20161118025959_aec0809e-d542-407b-a7ae-e21ccf1985a5): grant select on database default to role reads
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20161118025959_aec0809e-d542-407b-a7ae-e21ccf1985a5); Time taken: 0.082 seconds
INFO  : Executing command(queryId=hive_20161118025959_aec0809e-d542-407b-a7ae-e21ccf1985a5): grant select on database default to role reads
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20161118025959_aec0809e-d542-407b-a7ae-e21ccf1985a5); Time taken: 0.05 seconds
INFO  : OK
No rows affected (0.14 seconds)
0: jdbc:hive2://localhost:10000/default> grant role reads to group selector;
INFO  : Compiling command(queryId=hive_20161118025959_f5d96ca0-e649-46dc-a968-1c9fa5d8c1ff): grant role reads to group selector
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20161118025959_f5d96ca0-e649-46dc-a968-1c9fa5d8c1ff); Time taken: 0.075 seconds
INFO  : Executing command(queryId=hive_20161118025959_f5d96ca0-e649-46dc-a968-1c9fa5d8c1ff): grant role reads to group selector
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20161118025959_f5d96ca0-e649-46dc-a968-1c9fa5d8c1ff); Time taken: 0.035 seconds
INFO  : OK
No rows affected (0.12 seconds)
```
* Grant read privilege for default.sample07 only to 'writes'
```
0: jdbc:hive2://localhost:10000/default> revoke all on database default from role writes;
INFO  : Compiling command(queryId=hive_20161118030000_cded9498-a68a-4fa7-a890-2cfad4531f42): revoke all on database default from role writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20161118030000_cded9498-a68a-4fa7-a890-2cfad4531f42); Time taken: 0.061 seconds
INFO  : Executing command(queryId=hive_20161118030000_cded9498-a68a-4fa7-a890-2cfad4531f42): revoke all on database default from role writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20161118030000_cded9498-a68a-4fa7-a890-2cfad4531f42); Time taken: 0.09 seconds
INFO  : OK
No rows affected (0.158 seconds)
0: jdbc:hive2://localhost:10000/default> grant select on default.sample_07 to role writes;
INFO  : Compiling command(queryId=hive_20161118030000_73b13251-eb91-43c2-b137-6eca3c2624ad): grant select on default.sample_07 to role writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20161118030000_73b13251-eb91-43c2-b137-6eca3c2624ad); Time taken: 0.058 seconds
INFO  : Executing command(queryId=hive_20161118030000_73b13251-eb91-43c2-b137-6eca3c2624ad): grant select on default.sample_07 to role writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20161118030000_73b13251-eb91-43c2-b137-6eca3c2624ad); Time taken: 0.052 seconds
INFO  : OK
No rows affected (0.119 seconds)
0: jdbc:hive2://localhost:10000/default> grant role writes to group inserters;
INFO  : Compiling command(queryId=hive_20161118030000_5f0df9b4-85e5-40a0-b490-2d72541f1a53): grant role writes to group inserters
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20161118030000_5f0df9b4-85e5-40a0-b490-2d72541f1a53); Time taken: 0.059 seconds
INFO  : Executing command(queryId=hive_20161118030000_5f0df9b4-85e5-40a0-b490-2d72541f1a53): grant role writes to group inserters
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20161118030000_5f0df9b4-85e5-40a0-b490-2d72541f1a53); Time taken: 0.033 seconds
INFO  : OK
No rows affected (0.1 seconds)
```
* kinit as george
[root@ip-172-31-11-226 ~]# su george
[george@ip-172-31-11-226 root]$ klist
klist: No credentials cache found (ticket cache FILE:/tmp/krb5cc_1100)
[george@ip-172-31-11-226 root]$ kinit
Password for george@MSL-KYBEIDOS.COM:
[george@ip-172-31-11-226 root]$ beeline
Beeline version 1.1.0-cdh5.8.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-11-226.eu-central-1.compute.internal@MSL-KYBEIDOS.COM
scan complete in 3ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-11-226.eu-central-1.compute.internal@MSL-KYBEIDOS.COM
Enter username for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-11-226.eu-central-1.compute.internal@MSL-KYBEIDOS.COM: george
Enter password for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-11-226.eu-central-1.compute.internal@MSL-KYBEIDOS.COM: ******
Connected to: Apache Hive (version 1.1.0-cdh5.8.3)
Driver: Hive JDBC (version 1.1.0-cdh5.8.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20161118030303_493c4971-c465-4ea1-ace1-61c2d70b015a): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20161118030303_493c4971-c465-4ea1-ace1-61c2d70b015a); Time taken: 0.067 seconds
INFO  : Executing command(queryId=hive_20161118030303_493c4971-c465-4ea1-ace1-61c2d70b015a): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20161118030303_493c4971-c465-4ea1-ace1-61c2d70b015a); Time taken: 0.15 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.351 seconds)
```
* kinit as ferdinand
```
[root@ip-172-31-11-226 ~]# su ferdinand
[ferdinand@ip-172-31-11-226 root]$ kinit
Password for ferdinand@MSL-KYBEIDOS.COM:
[ferdinand@ip-172-31-11-226 root]$ beeline
Beeline version 1.1.0-cdh5.8.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-11-226.eu-central-1.compute.internal@MSL-KYBEIDOS.COM
scan complete in 3ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-11-226.eu-central-1.compute.internal@MSL-KYBEIDOS.COM
Enter username for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-11-226.eu-central-1.compute.internal@MSL-KYBEIDOS.COM: ferdinand
Enter password for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-11-226.eu-central-1.compute.internal@MSL-KYBEIDOS.COM: *********
Connected to: Apache Hive (version 1.1.0-cdh5.8.3)
Driver: Hive JDBC (version 1.1.0-cdh5.8.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20161118030404_8400aa2f-9020-459c-86ce-42fbf007aa9a): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20161118030404_8400aa2f-9020-459c-86ce-42fbf007aa9a); Time taken: 0.068 seconds
INFO  : Executing command(queryId=hive_20161118030404_8400aa2f-9020-459c-86ce-42fbf007aa9a): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20161118030404_8400aa2f-9020-459c-86ce-42fbf007aa9a); Time taken: 0.133 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
+------------+--+
1 row selected (0.326 seconds)
```
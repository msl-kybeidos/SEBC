```
[root@ip-172-31-9-123 yum.repos.d]# ls /etc/yum.repos.d/
CentOS-Base.repo       CentOS-fasttrack.repo  CentOS-Vault.repo      mysql-community.repo
CentOS-Debuginfo.repo  CentOS-Media.repo      cloudera-manager.repo
```
* scm User Grants
	* had to take the rights away first since i was to fast not reading ahead. But for proof the grants table prior to the grant
	```
	mysql> SELECT * from information_schema.user_privileges;
	+---------------------------------------+---------------+-------------------------+--------------+
	| GRANTEE                               | TABLE_CATALOG | PRIVILEGE_TYPE          | IS_GRANTABLE |
	+---------------------------------------+---------------+-------------------------+--------------+
	| 'root'@'localhost'                    | def           | SELECT                  | YES          |
	| 'root'@'localhost'                    | def           | INSERT                  | YES          |
	| 'root'@'localhost'                    | def           | UPDATE                  | YES          |
	| 'root'@'localhost'                    | def           | DELETE                  | YES          |
	| 'root'@'localhost'                    | def           | CREATE                  | YES          |
	| 'root'@'localhost'                    | def           | DROP                    | YES          |
	| 'root'@'localhost'                    | def           | RELOAD                  | YES          |
	| 'root'@'localhost'                    | def           | SHUTDOWN                | YES          |
	| 'root'@'localhost'                    | def           | PROCESS                 | YES          |
	| 'root'@'localhost'                    | def           | FILE                    | YES          |
	| 'root'@'localhost'                    | def           | REFERENCES              | YES          |
	| 'root'@'localhost'                    | def           | INDEX                   | YES          |
	| 'root'@'localhost'                    | def           | ALTER                   | YES          |
	| 'root'@'localhost'                    | def           | SHOW DATABASES          | YES          |
	| 'root'@'localhost'                    | def           | SUPER                   | YES          |
	| 'root'@'localhost'                    | def           | CREATE TEMPORARY TABLES | YES          |
	| 'root'@'localhost'                    | def           | LOCK TABLES             | YES          |
	| 'root'@'localhost'                    | def           | EXECUTE                 | YES          |
	| 'root'@'localhost'                    | def           | REPLICATION SLAVE       | YES          |
	| 'root'@'localhost'                    | def           | REPLICATION CLIENT      | YES          |
	| 'root'@'localhost'                    | def           | CREATE VIEW             | YES          |
	| 'root'@'localhost'                    | def           | SHOW VIEW               | YES          |
	| 'root'@'localhost'                    | def           | CREATE ROUTINE          | YES          |
	| 'root'@'localhost'                    | def           | ALTER ROUTINE           | YES          |
	| 'root'@'localhost'                    | def           | CREATE USER             | YES          |
	| 'root'@'localhost'                    | def           | EVENT                   | YES          |
	| 'root'@'localhost'                    | def           | TRIGGER                 | YES          |
	| 'root'@'localhost'                    | def           | CREATE TABLESPACE       | YES          |
	| 'root'@'ip-172-31-9-122.ec2.internal' | def           | SELECT                  | YES          |
	| 'root'@'ip-172-31-9-122.ec2.internal' | def           | INSERT                  | YES          |
	| 'root'@'ip-172-31-9-122.ec2.internal' | def           | UPDATE                  | YES          |
	| 'root'@'ip-172-31-9-122.ec2.internal' | def           | DELETE                  | YES          |
	| 'root'@'ip-172-31-9-122.ec2.internal' | def           | CREATE                  | YES          |
	| 'root'@'ip-172-31-9-122.ec2.internal' | def           | DROP                    | YES          |
	| 'root'@'ip-172-31-9-122.ec2.internal' | def           | RELOAD                  | YES          |
	| 'root'@'ip-172-31-9-122.ec2.internal' | def           | SHUTDOWN                | YES          |
	| 'root'@'ip-172-31-9-122.ec2.internal' | def           | PROCESS                 | YES          |
	| 'root'@'ip-172-31-9-122.ec2.internal' | def           | FILE                    | YES          |
	| 'root'@'ip-172-31-9-122.ec2.internal' | def           | REFERENCES              | YES          |
	| 'root'@'ip-172-31-9-122.ec2.internal' | def           | INDEX                   | YES          |
	| 'root'@'ip-172-31-9-122.ec2.internal' | def           | ALTER                   | YES          |
	| 'root'@'ip-172-31-9-122.ec2.internal' | def           | SHOW DATABASES          | YES          |
	| 'root'@'ip-172-31-9-122.ec2.internal' | def           | SUPER                   | YES          |
	| 'root'@'ip-172-31-9-122.ec2.internal' | def           | CREATE TEMPORARY TABLES | YES          |
	| 'root'@'ip-172-31-9-122.ec2.internal' | def           | LOCK TABLES             | YES          |
	| 'root'@'ip-172-31-9-122.ec2.internal' | def           | EXECUTE                 | YES          |
	| 'root'@'ip-172-31-9-122.ec2.internal' | def           | REPLICATION SLAVE       | YES          |
	| 'root'@'ip-172-31-9-122.ec2.internal' | def           | REPLICATION CLIENT      | YES          |
	| 'root'@'ip-172-31-9-122.ec2.internal' | def           | CREATE VIEW             | YES          |
	| 'root'@'ip-172-31-9-122.ec2.internal' | def           | SHOW VIEW               | YES          |
	| 'root'@'ip-172-31-9-122.ec2.internal' | def           | CREATE ROUTINE          | YES          |
	| 'root'@'ip-172-31-9-122.ec2.internal' | def           | ALTER ROUTINE           | YES          |
	| 'root'@'ip-172-31-9-122.ec2.internal' | def           | CREATE USER             | YES          |
	| 'root'@'ip-172-31-9-122.ec2.internal' | def           | EVENT                   | YES          |
	| 'root'@'ip-172-31-9-122.ec2.internal' | def           | TRIGGER                 | YES          |
	| 'root'@'ip-172-31-9-122.ec2.internal' | def           | CREATE TABLESPACE       | YES          |
	| 'root'@'127.0.0.1'                    | def           | SELECT                  | YES          |
	| 'root'@'127.0.0.1'                    | def           | INSERT                  | YES          |
	| 'root'@'127.0.0.1'                    | def           | UPDATE                  | YES          |
	| 'root'@'127.0.0.1'                    | def           | DELETE                  | YES          |
	| 'root'@'127.0.0.1'                    | def           | CREATE                  | YES          |
	| 'root'@'127.0.0.1'                    | def           | DROP                    | YES          |
	| 'root'@'127.0.0.1'                    | def           | RELOAD                  | YES          |
	| 'root'@'127.0.0.1'                    | def           | SHUTDOWN                | YES          |
	| 'root'@'127.0.0.1'                    | def           | PROCESS                 | YES          |
	| 'root'@'127.0.0.1'                    | def           | FILE                    | YES          |
	| 'root'@'127.0.0.1'                    | def           | REFERENCES              | YES          |
	| 'root'@'127.0.0.1'                    | def           | INDEX                   | YES          |
	| 'root'@'127.0.0.1'                    | def           | ALTER                   | YES          |
	| 'root'@'127.0.0.1'                    | def           | SHOW DATABASES          | YES          |
	| 'root'@'127.0.0.1'                    | def           | SUPER                   | YES          |
	| 'root'@'127.0.0.1'                    | def           | CREATE TEMPORARY TABLES | YES          |
	| 'root'@'127.0.0.1'                    | def           | LOCK TABLES             | YES          |
	| 'root'@'127.0.0.1'                    | def           | EXECUTE                 | YES          |
	| 'root'@'127.0.0.1'                    | def           | REPLICATION SLAVE       | YES          |
	| 'root'@'127.0.0.1'                    | def           | REPLICATION CLIENT      | YES          |
	| 'root'@'127.0.0.1'                    | def           | CREATE VIEW             | YES          |
	| 'root'@'127.0.0.1'                    | def           | SHOW VIEW               | YES          |
	| 'root'@'127.0.0.1'                    | def           | CREATE ROUTINE          | YES          |
	| 'root'@'127.0.0.1'                    | def           | ALTER ROUTINE           | YES          |
	| 'root'@'127.0.0.1'                    | def           | CREATE USER             | YES          |
	| 'root'@'127.0.0.1'                    | def           | EVENT                   | YES          |
	| 'root'@'127.0.0.1'                    | def           | TRIGGER                 | YES          |
	| 'root'@'127.0.0.1'                    | def           | CREATE TABLESPACE       | YES          |
	| 'root'@'::1'                          | def           | SELECT                  | YES          |
	| 'root'@'::1'                          | def           | INSERT                  | YES          |
	| 'root'@'::1'                          | def           | UPDATE                  | YES          |
	| 'root'@'::1'                          | def           | DELETE                  | YES          |
	| 'root'@'::1'                          | def           | CREATE                  | YES          |
	| 'root'@'::1'                          | def           | DROP                    | YES          |
	| 'root'@'::1'                          | def           | RELOAD                  | YES          |
	| 'root'@'::1'                          | def           | SHUTDOWN                | YES          |
	| 'root'@'::1'                          | def           | PROCESS                 | YES          |
	| 'root'@'::1'                          | def           | FILE                    | YES          |
	| 'root'@'::1'                          | def           | REFERENCES              | YES          |
	| 'root'@'::1'                          | def           | INDEX                   | YES          |
	| 'root'@'::1'                          | def           | ALTER                   | YES          |
	| 'root'@'::1'                          | def           | SHOW DATABASES          | YES          |
	| 'root'@'::1'                          | def           | SUPER                   | YES          |
	| 'root'@'::1'                          | def           | CREATE TEMPORARY TABLES | YES          |
	| 'root'@'::1'                          | def           | LOCK TABLES             | YES          |
	| 'root'@'::1'                          | def           | EXECUTE                 | YES          |
	| 'root'@'::1'                          | def           | REPLICATION SLAVE       | YES          |
	| 'root'@'::1'                          | def           | REPLICATION CLIENT      | YES          |
	| 'root'@'::1'                          | def           | CREATE VIEW             | YES          |
	| 'root'@'::1'                          | def           | SHOW VIEW               | YES          |
	| 'root'@'::1'                          | def           | CREATE ROUTINE          | YES          |
	| 'root'@'::1'                          | def           | ALTER ROUTINE           | YES          |
	| 'root'@'::1'                          | def           | CREATE USER             | YES          |
	| 'root'@'::1'                          | def           | EVENT                   | YES          |
	| 'root'@'::1'                          | def           | TRIGGER                 | YES          |
	| 'root'@'::1'                          | def           | CREATE TABLESPACE       | YES          |
	| 'rman'@'%'                            | def           | USAGE                   | NO           |
	| 'hive'@'%'                            | def           | USAGE                   | NO           |
	| 'oozie'@'%'                           | def           | USAGE                   | NO           |
	| 'hue'@'%'                             | def           | USAGE                   | NO           |
	| 'sentry'@'%'                          | def           | USAGE                   | NO           |
	+---------------------------------------+---------------+-------------------------+--------------+
	117 rows in set (0.00 sec)
	
	mysql> grant all on scm.* TO 'scm'@'ip-172-31-9-123.ec2.internal' IDENTIFIED BY 'scm_password';
	Query OK, 0 rows affected (0.00 sec)
	
	mysql> grant all on scm.* to 'scm'@'172.31.9.123' identified by 'scm_password';
	Query OK, 0 rows affected (0.00 sec)
	```

* SCM Database preparation
 ```
 [root@ip-172-31-9-123 /]# /usr/share/cmf/schema/scm_prepare_database.sh -h ip-172-31-9-122.ec2.internal mysql scm scm scm_password
	JAVA_HOME=/usr/java/jdk1.7.0_67-cloudera
	Verifying that we can write to /etc/cloudera-scm-server
	Creating SCM configuration file in /etc/cloudera-scm-server
	Executing:  /usr/java/jdk1.7.0_67-cloudera/bin/java -cp /usr/share/java/mysql-connector-java.jar:/usr/	share/java/oracle-connector-java.jar:/usr/share/cmf/schema/../lib/* 	com.cloudera.enterprise.dbutil.DbCommandExecutor /etc/cloudera-scm-server/db.properties 	com.cloudera.cmf.db.
	log4j:ERROR Could not find value for key log4j.appender.A
	log4j:ERROR Could not instantiate appender named "A".
	[2016-11-18 09:06:52,325] INFO     0[main] - 	com.cloudera.enterprise.dbutil.DbCommandExecutor.testDbConnection(DbCommandExecutor.java) - 	Successfully connected to database.
	All done, your SCM database is configured correctly!
	```

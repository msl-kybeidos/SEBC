* Grants for Databases
```
mysql> show grants for rman;
+-----------------------------------------------------------------------------------------------------+
| Grants for rman@%                                                                                   |
+-----------------------------------------------------------------------------------------------------+
| GRANT USAGE ON *.* TO 'rman'@'%' IDENTIFIED BY PASSWORD '*AEF345BFE495D8E678EA9D3D5708FD110AD2F08E' |
| GRANT ALL PRIVILEGES ON `rman`.* TO 'rman'@'%'                                                      |
+-----------------------------------------------------------------------------------------------------+
2 rows in set (0.00 sec)

mysql> show grants for hive;
+-----------------------------------------------------------------------------------------------------+
| Grants for hive@%                                                                                   |
+-----------------------------------------------------------------------------------------------------+
| GRANT USAGE ON *.* TO 'hive'@'%' IDENTIFIED BY PASSWORD '*8AC2E431CC7A9F2C4C0E51A65B8D8175892D9F22' |
| GRANT ALL PRIVILEGES ON `hive`.* TO 'hive'@'%'                                                      |
+-----------------------------------------------------------------------------------------------------+
2 rows in set (0.00 sec)

mysql> show grants for scm;
ERROR 1141 (42000): There is no such grant defined for user 'scm' on host '%'
mysql> show grants for 'scm'@'ip-172-31-9-123.ec2.internal';
+-------------------------------------------------------------------------------------------------------------------------------+
| Grants for scm@ip-172-31-9-123.ec2.internal                                                                                   |
+-------------------------------------------------------------------------------------------------------------------------------+
| GRANT USAGE ON *.* TO 'scm'@'ip-172-31-9-123.ec2.internal' IDENTIFIED BY PASSWORD '*E2D6A4ADCCA7B38098E85EAF9BB785AB21451139' |
| GRANT ALL PRIVILEGES ON `scm`.* TO 'scm'@'ip-172-31-9-123.ec2.internal'                                                       |
+-------------------------------------------------------------------------------------------------------------------------------+
2 rows in set (0.00 sec)
```
* HDFS LS
```
[hdfs@ip-172-31-9-123 init.d]$ hdfs dfs -ls /user
Found 6 items
drwxr-xr-x   - bavaria social              0 2016-11-18 10:05 /user/bavaria
drwxrwxrwx   - mapred  hadoop              0 2016-11-18 09:54 /user/history
drwxrwxr-t   - hive    hive                0 2016-11-18 09:55 /user/hive
drwxrwxr-x   - hue     hue                 0 2016-11-18 09:56 /user/hue
drwxrwxr-x   - oozie   oozie               0 2016-11-18 09:56 /user/oozie
drwxr-xr-x   - saxony  democratic          0 2016-11-18 10:05 /user/saxony
```

* CM API Call
```
{
  "items" : [ {
    "hostId" : "i-9850bc00",
    "ipAddress" : "172.31.9.122",
    "hostname" : "ip-172-31-9-122.ec2.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-9-123.ec2.internal:7180/cmf/hostRedirect/i-9850bc00",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15664750592
  }, {
    "hostId" : "i-9b50bc03",
    "ipAddress" : "172.31.9.123",
    "hostname" : "ip-172-31-9-123.ec2.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-9-123.ec2.internal:7180/cmf/hostRedirect/i-9b50bc03",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15664750592
  }, {
    "hostId" : "i-9a50bc02",
    "ipAddress" : "172.31.9.124",
    "hostname" : "ip-172-31-9-124.ec2.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-9-123.ec2.internal:7180/cmf/hostRedirect/i-9a50bc02",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15664750592
  }, {
    "hostId" : "i-9d50bc05",
    "ipAddress" : "172.31.9.125",
    "hostname" : "ip-172-31-9-125.ec2.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-9-123.ec2.internal:7180/cmf/hostRedirect/i-9d50bc05",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15664750592
  }, {
    "hostId" : "i-9c50bc04",
    "ipAddress" : "172.31.9.126",
    "hostname" : "ip-172-31-9-126.ec2.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-9-123.ec2.internal:7180/cmf/hostRedirect/i-9c50bc04",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15664750592
  } ]
}
```

* Teragen command
```
[bavaria@ip-172-31-9-123 hadoop-mapreduce]$ pwd
/opt/cloudera/parcels/CDH/lib/hadoop-mapreduce
[bavaria@ip-172-31-9-123 hadoop-mapreduce]$ time hadoop jar hadoop-mapreduce-examples.jar teragen -Dmapreduce.job.maps=4 -Ddfs.blocksize=16M 51200000 /user/bavaria/tgen512m
```

* time output
```
real    2m34.817s
user    0m5.998s
sys     0m0.328s
```

* hdfs ls
```
[bavaria@ip-172-31-9-123 hadoop-mapreduce]$ hdfs dfs -ls /user/bavaria/tgen512m
Found 5 items
-rw-r--r--   3 bavaria social          0 2016-11-18 10:30 /user/bavaria/tgen512m/_SUCCESS
-rw-r--r--   3 bavaria social 1280000000 2016-11-18 10:30 /user/bavaria/tgen512m/part-m-00000
-rw-r--r--   3 bavaria social 1280000000 2016-11-18 10:30 /user/bavaria/tgen512m/part-m-00001
-rw-r--r--   3 bavaria social 1280000000 2016-11-18 10:30 /user/bavaria/tgen512m/part-m-00002
-rw-r--r--   3 bavaria social 1280000000 2016-11-18 10:29 /user/bavaria/tgen512m/part-m-00003
```

* hdfs blocks
```
[bavaria@ip-172-31-9-123 hadoop-mapreduce]$ hdfs fsck /user/bavaria/tgen512m -blocks
Connecting to namenode via http://ip-172-31-9-122.ec2.internal:50070
FSCK started by bavaria (auth:SIMPLE) from /172.31.9.123 for path /user/bavaria/tgen512m at Fri Nov 18 10:36:40 UTC 2016
.....Status: HEALTHY
 Total size:    5120000000 B
 Total dirs:    1
 Total files:   5
 Total symlinks:                0
 Total blocks (validated):      308 (avg. block size 16623376 B)
 Minimally replicated blocks:   308 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          4
 Number of racks:               1
FSCK ended at Fri Nov 18 10:36:40 UTC 2016 in 15 milliseconds


The filesystem under path '/user/bavaria/tgen512m' is HEALTHY
```
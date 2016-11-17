* Create a precious directory in HDFS; copy the ZIP course file into it.<br />
**hdfs dfs -mkdir /precious**<br />
**hdfs dfs copyFromLocal /tmp/SEBC-master.zip /precious**
* Enable snapshots for precious<br />
**hdfs dfsadmin -allowSnapshot /precious**<br />
Allowing snaphot on /precious succeeded
* Create a snapshot called sebc-hdfs-test<br />
**hdfs dfs -createSnapshot /precious sebc-hdfs-test**
Created snapshot /precious/.snapshot/sebc-hdfs-test
* Delete the directory<br />
**hdfs dfs -rm -r /precious**<br />
rm: Failed to move to trash: hdfs://ip-172-31-11-226.eu-central-1.compute.internal:8020/precious: The directory /precious cannot be deleted since /precious is snapshottable and already has snapshots
* Delete the ZIP file<br />
**hdfs dfs -rm -skipTrash /precious/SEBC-master.zip**<br />
Deleted /precious/SEBC-master.zip
* Restore the deleted file
```shell
[hdfs@ip-172-31-11-226 root]$ hdfs dfs -ls /precious
[hdfs@ip-172-31-11-226 root]$ hdfs dfs -cp /precious/.snapshot/sebc-hdfs-test/SEBC-master.zip /precious
[hdfs@ip-172-31-11-226 root]$ hdfs dfs -ls /precious
Found 1 items
-rw-r--r--   3 hdfs supergroup     410158 2016-11-17 08:54 /precious/SEBC-master.zip
```
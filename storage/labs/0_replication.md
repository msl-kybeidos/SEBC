Namenode from destination Cluster seems to be sending the private IP-Addresses of the Datanodes, so the Hosts from source Cluster cannot reach them. There is an option to make the cluster use Hostnames instead of ip addresses:(You can look for in Cloudera Manager Search and get it spread out to the cluster)<br />
```xml
<property>
        <name>dfs.client.use.datanode.hostname</name>
        <value>true</value>
</property>
```
Cluster A now does not get private IP-Addresses but private DNS-Names, so all the Machines on the source Cluster have to be told where to find those Machines so you have to insert the pairs of **public** IP-Addresses and **private** DNS-Hostnames into the hosts file.

This has to be done on every machine since the datanodes from the both clusters talk to each other directly. 

Once done you can call the distcp command successfully:

**hadoop distcp hdfs://nameservice1/user/gerhje/forpawel/ hdfs://35.156.44.154/forhajo/**
* What is ubertask optimization?<br />
	In an default job the Resource Manager creates seperate Containers for Mapper and Reducer. When the job is "small enough" the Resource Manager can make the map and reduce task run in the Application Master Process sparing the machine to create the overhead associated with creating each container.<br />
	The parameters on which the decision will be based can be altered in Cloudera Manager:
	* mapreduce.job.ubertask.maxmaps (default 9)
	* mapreduce.job.ubertask.maxreduces (default 1)
	* mapreduce.job.ubertask.maxbytes (default 0Gib)
	* mapreduce.job.ubertask.enable (default disabled)

* Where in CM is the Kerberos Security Realm value displayed?
	* under Administration -> Settings -> Kerberos -> Kerberos Security Realm
	* can also be found over searchfield when staring to type realm

* Which CDH service(s) host a property for enabling Kerberos authentication?
	* ZooKeeper
	* HDFS (for webconsole)
	* YARN (for webconsole)

* How do you upgrade the CM agents?
	* http://www.cloudera.com/documentation/enterprise/5-8-x/topics/cm_ag_ug_cm5.html#cmig_topic_9_4_10
	* stop services
	* (if necessary) update jdk
	* stop cloudera manager server
	* stop cloudera manager agent
	* update yum repository to desired version 
	* yum upgrade cloudera-mamager-server cloudera-manager-daemons cloudera-manager-agent
	* let cloudera manager install updates on all hosts or stop services on all hosts and follow above procedures
	*   

* Give the tsquery statement used to chart Hue's CPU utilization?
	* select cpu_system_rate + cpu_user_rate where serviceType= HUE
* Name all the roles that make up the Hive service
	* WebHCat Server
	* Hive Server
	* Gateway
	* Hive Metastore Server
* What steps must be completed before integrating Cloudera Manager with Kerberos?
	* Enable TLS Encryption because keytabs are getting send over network during installation
	* Install JCE Unlimited Strength thingi for AES-256 encryption
	* Create Principal for CMS

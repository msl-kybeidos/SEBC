* Create an end-user Linux account named with your GitHub handle<br />
	**useradd msl-kybeidos**<br />
	**passwd msl-kybeidos**<br />

	* Create a home HDFS directory for this user as well<br />
  	**su hdfs**<br />
  	**hdfs dfs -mkdir /user/msl-kybeidos**
  *Run the following exercises as this user
  	**su msl-kybeidos**<br />
    
* The jar used from here resides in /opt/cloudera/parcels/CDH-5.8.3-1.cdh5.8.3.p0.2/jars/

* Create a 10 GB file using teragen
	* Set the number of mappers to four
  * Limit the block size to 32 MB
  * Land the result under your user's home directory
  * Use the time command to report the job's duration<br />
  **time hadoop jar hadoop-examples.jar teragen -Dmapreduce.job.maps=4 -Ddfs.blocksize=32M 100000000 /user/msl-kybeidos/teragen**<br />
  real    1m57.815s<br />
	user    0m6.925s<br />
	sys     0m0.419s<br />

* Run the terasort command on this file
	* Use the time command to report the job's duration
  * Land the result under your user's home directory<br />
  **time hadoop jar hadoop-examples.jar terasort /user/msl-kybeidos/teragen /user/msl-kybeidos/terasort**<br />
  real    5m24.716s<br />
	user    0m9.994s<br />
	sys     0m0.524s<br />






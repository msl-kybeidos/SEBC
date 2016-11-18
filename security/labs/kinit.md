```
[msl-kybeidos@ip-172-31-11-226 root]$ klist
klist: No credentials cache found (ticket cache FILE:/tmp/krb5cc_501)
[msl-kybeidos@ip-172-31-11-226 root]$ hdfs dfs -ls /
16/11/18 01:34:05 WARN security.UserGroupInformation: PriviledgedActionException as:msl-kybeidos (auth:KERBEROS) cause:javax.security.sasl.SaslException: GSS initiate failed [Caused by GSSException: No valid credentials provided (Mechanism level: Failed to find any Kerberos tgt)]
16/11/18 01:34:05 WARN ipc.Client: Exception encountered while connecting to the server : javax.security.sasl.SaslException: GSS initiate failed [Caused by GSSException: No valid credentials provided (Mechanism level: Failed to find any Kerberos tgt)]
....
[msl-kybeidos@ip-172-31-11-226 root]$ kinit
Password for msl-kybeidos@MSL-KYBEIDOS.COM:
[msl-kybeidos@ip-172-31-11-226 root]$ klist
Ticket cache: FILE:/tmp/krb5cc_501
Default principal: msl-kybeidos@MSL-KYBEIDOS.COM

Valid starting     Expires            Service principal
11/18/16 01:34:15  11/19/16 01:34:15  krbtgt/MSL-KYBEIDOS.COM@MSL-KYBEIDOS.COM
        renew until 11/25/16 01:34:15
[msl-kybeidos@ip-172-31-11-226 root]$ hdfs dfs -ls /
Found 4 items
drwxr-xr-x   - hdfs supergroup          0 2016-11-17 09:18 /precious
drwxr-xr-x   - hdfs supergroup          0 2016-11-17 21:58 /results
drwxrwxrwx   - hdfs supergroup          0 2016-11-18 00:11 /tmp
drwxr-xr-x   - hdfs supergroup          0 2016-11-17 09:25 /user
```
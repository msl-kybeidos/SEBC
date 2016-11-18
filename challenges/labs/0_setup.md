* Region
	* US East - North Virginia
* AMI ID
	* ami-1c221e76
* OS
	* CentOS 6 (x86_64) - with Updates HVM - basically an more or less current CentOS 6.8
* Volume Space
	```
	[root@ip-172-31-9-122 ~]# df -h
	Filesystem      Size  Used Avail Use% Mounted on
	/dev/xvda1       74G  754M   70G   2% /
	tmpfs           7.3G     0  7.3G   0% /dev/shm
	[root@ip-172-31-9-122 ~]# simsh !!
	simsh df -h
	Node4: tmpfs           7.3G     0  7.3G   0% /dev/shm
	Node4: /dev/xvda1       74G  712M   70G   1% /
	Node4: Filesystem      Size  Used Avail Use% Mounted on
	Node1: tmpfs           7.3G     0  7.3G   0% /dev/shm
	Node1: /dev/xvda1       74G  713M   70G   1% /
	Node1: Filesystem      Size  Used Avail Use% Mounted on
	Node3: tmpfs           7.3G     0  7.3G   0% /dev/shm
	Node3: /dev/xvda1       74G  712M   70G   1% /
	Node3: Filesystem      Size  Used Avail Use% Mounted on
	Node2: tmpfs           7.3G     0  7.3G   0% /dev/shm
	Node2: /dev/xvda1       74G  712M   70G   1% /
	Node2: Filesystem      Size  Used Avail Use% Mounted on
  ```
* Enalbled Repository Lists
	```
	[root@ip-172-31-9-122 ~]# yum repolist enabled
	Loaded plugins: fastestmirror, presto
	Loading mirror speeds from cached hostfile
	 * base: mirror.math.princeton.edu
	 * extras: mirror.trouble-free.net
	 * updates: mirror.netdepot.com
	repo id                             repo name                                      status
	base                                CentOS-6 - Base                                6,696
	extras                              CentOS-6 - Extras                                 62
	updates                             CentOS-6 - Updates                               603
	repolist: 7,361
	[root@ip-172-31-9-122 ~]# simsh !!
	simsh yum repolist enabled
	Node2: repolist: 7,361
	Node2: updates                        CentOS-6 - Updates                           603
	Node2: extras                         CentOS-6 - Extras                             62
	Node2: base                           CentOS-6 - Base                            6,696
	Node2: repo id                        repo name                                  status
	Node2:  * updates: mirror.netdepot.com
	Node2:  * extras: mirror.trouble-free.net
	Node2:  * base: mirror.math.princeton.edu
	Node2: Loading mirror speeds from cached hostfile
	Node2: Loaded plugins: fastestmirror, presto
	Node3: repolist: 7,361
	Node3: updates                        CentOS-6 - Updates                           603
	Node3: extras                         CentOS-6 - Extras                             62
	Node3: base                           CentOS-6 - Base                            6,696
	Node3: repo id                        repo name                                  status
	Node3:  * updates: mirror.netdepot.com
	Node3:  * extras: ftp.osuosl.org
	Node3:  * base: mirror.math.princeton.edu
	Node3: Loading mirror speeds from cached hostfile
	Node3: Loaded plugins: fastestmirror, presto
	Node4: repolist: 7,361
	Node4: updates                        CentOS-6 - Updates                           603
	Node4: extras                         CentOS-6 - Extras                             62
	Node4: base                           CentOS-6 - Base                            6,696
	Node4: repo id                        repo name                                  status
	Node4:  * updates: mirror.netdepot.com
	Node4:  * extras: mirror.trouble-free.net
	Node4:  * base: mirror.cisp.com
	Node4: Loading mirror speeds from cached hostfile
	Node4: Loaded plugins: fastestmirror, presto
	Node1: repolist: 7,361
	Node1: updates                        CentOS-6 - Updates                           603
	Node1: extras                         CentOS-6 - Extras                             62
	Node1: base                           CentOS-6 - Base                            6,696
	Node1: repo id                        repo name                                  status
	Node1:  * updates: linux.cc.lehigh.edu
	Node1:  * extras: mirror.trouble-free.net
	Node1:  * base: mirror.cisp.com
	Node1: Loading mirror speeds from cached hostfile
	Node1: Loaded plugins: fastestmirror, presto
	```
* /etc/password
	* bavaria:x:2700:2700::/home/bavaria:/bin/bash
	* saxony:x:2800:2800::/home/saxony:/bin/bash
* /etc/group
	* democratic:x:2801:saxony
	* social:x:2802:bavaria


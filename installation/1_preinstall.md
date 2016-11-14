1. Check vm.swappiness on all your nodes<br />
	**cat /proc/sys/vm/swappiness** -> 60
	* Set the value to 1 if necessary<br />
	**sudo sysctl vm.swappiness=1 while system is running**<br />
	**for rebootproof config add vm.swappiness = 1 to /etc/sysctl.conf**


2. Show the mount attributes of all volumes	
	**mount -l**<br />
	/dev/xvda1 on / type ext4 (rw)<br />
	proc on /proc type proc (rw)<br />
	sysfs on /sys type sysfs (rw)<br />
	devpts on /dev/pts type devpts (rw,gid=5,mode=620)<br />
	tmpfs on /dev/shm type tmpfs (rw,rootcontext="system_u:object_r:tmpfs_t:s0")<br />
	none on /proc/sys/fs/binfmt_misc type binfmt_misc (rw)<br />
	/dev/xvdf on /someplace type ext4 (rw)<br />


3. Show the reserve space of any non-root, ext-based volumes<br />
	*Had to create one first*<br />
	**df -h -t ext4**<br />
	Filesystem      Size  Used Avail Use% Mounted on<br />
	/dev/xvda1      7.8G  666M  6.7G   9% /<br />
	/dev/xvdf       9.8G   23M  9.2G   1% /someplace<br />

4. Show that transparent hugepages is disabled **Please give feadback if there is another better solution**<br />
	**cat /sys/kernel/mm/transparent_hugepage/enabled**<br />
	disabled if showing **always madvise [never]**<br />
	Bootup Otion in grub.conf only changed /sys/kernel/mm/transparent_hugepage/enabled but not /sys/kernel/mm/transparent_hugepage/defrag<br />
	found solution with startup skript: https://answers.splunk.com/answers/401192/disable-thp-in-aws-linux-ami.html
	/etc/init.d/disable-transparent-hugepages skript now runs at startup<br />
	now all four transparent_hugepage/enable, transparent_hugepage/defrag, redhat_transparent_hugepage/enable, redhat_transparent_hugepage/defrag is disabled and showing **always madvise [never]**

5. Report the network interface attributes<br />
	**ifconfig**<br />
	**eth0**      Link encap:Ethernet  HWaddr 02:AE:72:72:37:DD<br />
          inet addr:172.31.7.178  Bcast:172.31.15.255  Mask:255.255.240.0<br />
          inet6 addr: fe80::ae:72ff:fe72:37dd/64 Scope:Link<br />
          UP BROADCAST RUNNING MULTICAST  MTU:9001  Metric:1<br />
          RX packets:316 errors:0 dropped:0 overruns:0 frame:0<br />
          TX packets:313 errors:0 dropped:0 overruns:0 carrier:0<br />
          collisions:0 txqueuelen:1000<br />
          RX bytes:35764 (34.9 KiB)  TX bytes:38227 (37.3 KiB)<br />
          Interrupt:144<br />
**lo**        Link encap:Local Loopback<br />
          inet addr:127.0.0.1  Mask:255.0.0.0<br />
          inet6 addr: ::1/128 Scope:Host<br />
          UP LOOPBACK RUNNING  MTU:65536  Metric:1<br />
          RX packets:0 errors:0 dropped:0 overruns:0 frame:0<br />
          TX packets:0 errors:0 dropped:0 overruns:0 carrier:0<br />
          collisions:0 txqueuelen:0<br />
          RX bytes:0 (0.0 b)  TX bytes:0 (0.0 b)<br />

6. Show forward and reverse host lookups using getent and nslookup<br />
	forward-example: **getent hosts Node1** -> 35.156.86.105   node1<br />
	The standard CentOS6 AMI Image does not have nsloopup installed -> yum install bind-utils<br />
	backward example: **nslookup 35.156.86.105**<br />
	Server:         172.31.0.2<br />
	Address:        172.31.0.2#53<br />

	Non-authoritative answer:<br />
	105.86.156.35.in-addr.arpa      name = ec2-35-156-86-105.eu-central-1.compute.amazonaws.com

7. Verify the nscd service is running<br />
	*is also not installed on cent...:-(*<br />
	sudo yum install nscd<br />
	**service nscd status**<br />
	nscd (pid 1480) is running...

8. Verify the ntpd service is running<br />
	*is not installed on cent...*<br />
	sudo yum install ntp<br />
	**service ntpd status**<br />
	ntpd (pid  1607) is running...


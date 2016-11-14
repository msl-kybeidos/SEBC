1. Check vm.swappiness on all your nodes
	*cat /proc/sys/vm/swappiness -> 60
		* Set the value to 1 if necessary
			*sudo sysctl vm.swappiness=1

2. Show the mount attributes of all volumes	
	**mount -l**
	/dev/xvda1 on / type ext4 (rw)
	proc on /proc type proc (rw)
	sysfs on /sys type sysfs (rw)
	devpts on /dev/pts type devpts (rw,gid=5,mode=620)
	tmpfs on /dev/shm type tmpfs (rw,rootcontext="system_u:object_r:tmpfs_t:s0")
	none on /proc/sys/fs/binfmt_misc type binfmt_misc (rw)
	/dev/xvdf on /someplace type ext4 (rw)


3. Show the reserve space of any non-root, ext-based volumes
	*Had to create one first*
	**df -h -t ext4**
	Filesystem      Size  Used Avail Use% Mounted on
	/dev/xvda1      7.8G  666M  6.7G   9% /
	/dev/xvdf       9.8G   23M  9.2G   1% /someplace

4. Show that transparent hugepages is disabled **Please give feadback if there is another better solution**
	**cat /sys/kernel/mm/transparent_hugepage/enabled**
	disabled if showing **always madvise [never]**
	Bootup Otion in grub.conf only changed /sys/kernel/mm/transparent_hugepage/enabled but not /sys/kernel/mm/transparent_hugepage/defrag
	found solution with startup skript: https://answers.splunk.com/answers/401192/disable-thp-in-aws-linux-ami.html
	/etc/init.d/disable-transparent-hugepages skript now runs at startup
	now all four transparent_hugepage/enable, transparent_hugepage/defrag, redhat_transparent_hugepage/enable, redhat_transparent_hugepage/defrag is disabled and showing **always madvise [never]**

5. Report the network interface attributes
	**ifconfig**
	eth0      Link encap:Ethernet  HWaddr 02:AE:72:72:37:DD
          inet addr:172.31.7.178  Bcast:172.31.15.255  Mask:255.255.240.0
          inet6 addr: fe80::ae:72ff:fe72:37dd/64 Scope:Link
          UP BROADCAST RUNNING MULTICAST  MTU:9001  Metric:1
          RX packets:316 errors:0 dropped:0 overruns:0 frame:0
          TX packets:313 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000
          RX bytes:35764 (34.9 KiB)  TX bytes:38227 (37.3 KiB)
          Interrupt:144

lo        Link encap:Local Loopback
          inet addr:127.0.0.1  Mask:255.0.0.0
          inet6 addr: ::1/128 Scope:Host
          UP LOOPBACK RUNNING  MTU:65536  Metric:1
          RX packets:0 errors:0 dropped:0 overruns:0 frame:0
          TX packets:0 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:0
          RX bytes:0 (0.0 b)  TX bytes:0 (0.0 b)

6. Show forward and reverse host lookups using getent and nslookup
	forward-example: **getent hosts Node1** -> 35.156.86.105   node1
	The standard CentOS6 AMI Image does not have nsloopup installed -> yum install bind-utils
	backward example: **nslookup 35.156.86.105**
	Server:         172.31.0.2
	Address:        172.31.0.2#53

	Non-authoritative answer:
	105.86.156.35.in-addr.arpa      name = ec2-35-156-86-105.eu-central-1.compute.amazonaws.com

7. Verify the nscd service is running
	*is also not installed on cent...:-(*
	**service nscd status**
	nscd (pid 1480) is running...

8. Verify the ntpd service is running
	*is not installed on cent...*
	**service ntpd status**
	ntpd (pid  1607) is running...


* Teragen
	* one of the fastest
```
teragen 8-4-1024
=======================================
job.maps=8
map.memory.mb=1024
map.java.opts.max.heap=819

real    1m50.128s
user    0m6.043s
sys     0m0.332s

```
	* one of the slowest
	```
teragen 2-2-2048
=======================================
job.maps=2
map.memory.mb=2048
map.java.opts.max.heap=1638

real    2m20.545s
user    0m6.548s
sys     0m0.349s
```
* one of the fastest Terasort
```
===== terasort 2-8-1024 =====
job-maps=2
job.reduces=8
map.memory.mb=1024
map.java.opts.max.heap=819
reduce.memory.mb=1024
reduce.java.opts.max.heap=819

real    2m52.795s
user    0m8.959s
sys     0m0.460s
======================================
```
	* one of the slowest
```
===== terasort 2-2-2048 =====
job-maps=2
job.reduces=2
map.memory.mb=2048
map.java.opts.max.heap=1638
reduce.memory.mb=2048
reduce.java.opts.max.heap=1638

real    3m59.762s
user    0m9.168s
sys     0m0.475s
======================================
```	
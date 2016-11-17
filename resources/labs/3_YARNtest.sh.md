```shell
#!/bin/sh
# Confirm the path values given below correspond to your installation

HADOOP_MR=/opt/cloudera/parcels/CDH/lib/hadoop-mapreduce
# HADOOP_PATH=/opt/cloudera/parcels/CDH/bin

# Mark start of the loop
echo Testing loop started on `date`

# Mapper containers
for i in 2 4 8
do
   # Reducer containers
   for j in 2 4 8
   do
      # Container memory
      for k in 512 1024 2048
      do
         # Set mapper JVM heap
         MAP_MB=`echo "($k*0.8)/1" | bc`

         # Set reducer JVM heap
         RED_MB=`echo "($k*0.8)/1" | bc`

        echo teragen $i-$j-$k
        echo =======================================
        echo job.maps=$i
        echo map.memory.mb=$k
        echo map.java.opts.max.heap=$MAP_MB

        time hadoop jar $HADOOP_MR/hadoop-mapreduce-examples.jar teragen \
                     -Dmapreduce.job.maps=$i \
                     -Dmapreduce.map.memory.mb=$k \
                     -Dmapreduce.map.java.opts.max.heap=$MAP_MB \
                     100000000 /results/tg-10GB-${i}-${j}-${k} 1>tera_${i}_${j}_${k}.out 2>tera_${i}_${j}_${k}.err

        echo ===== terasort $i-$j-$k =====
        echo job-maps=$i
        echo job.reduces=$j
        echo map.memory.mb=$k
        echo map.java.opts.max.heap=$MAP_MB
        echo reduce.memory.mb=$k
        echo reduce.java.opts.max.heap=$RED_MB
       time hadoop jar $HADOOP_MR/hadoop-mapreduce-examples.jar terasort \
                     -Dmapreduce.job.maps=$i \
                     -Dmapreduce.job.reduces=$j \
                     -Dmapreduce.map.memory.mb=$k \
                     -Dmapreduce.map.java.opts.max.heap=$MAP_MB \
                     -Dmapreduce.reduce.memory.mb=$k \
                     -Dmapreduce.reduce.java.opts.max.heap=$RED_MB \
                     /results/tg-10GB-${i}-${j}-${k}  \
                     /results/ts-10GB-${i}-${j}-${k} 1>>tera_${i}_${j}_${k}.out 2>>tera_${i}_${j}_${k}.err

        echo ======================================
        hdfs dfs -rm -R -skipTrash /results/tg-10GB-${i}-${j}-${k}
        hdfs dfs -rm -R -skipTrash /results/ts-10GB-${i}-${j}-${k}
      done
   done
done

echo Testing loop ended on `date`
```
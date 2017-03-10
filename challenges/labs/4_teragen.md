1. teragen command and output:

  ```
    [neymar@ip-10-0-0-111 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapred.map.tasks=8 -D dfs.block.size=16m -Dmapred.map.tasks.speculative.execution=false 65536000 /user/neymar/tgen640
    17/03/10 09:44:29 INFO client.RMProxy: Connecting to ResourceManager at ip-10-0-0-111.eu-west-1.compute.internal/10.0.0.111:8032
    17/03/10 09:44:29 INFO terasort.TeraGen: Generating 65536000 using 8
    17/03/10 09:44:29 INFO mapreduce.JobSubmitter: number of splits:8
    17/03/10 09:44:29 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
    17/03/10 09:44:29 INFO Configuration.deprecation: mapred.map.tasks.speculative.execution is deprecated. Instead, use mapreduce.map.speculative
    17/03/10 09:44:29 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
    17/03/10 09:44:30 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1489137140207_0003
    17/03/10 09:44:30 INFO impl.YarnClientImpl: Submitted application application_1489137140207_0003
    17/03/10 09:44:30 INFO mapreduce.Job: The url to track the job: http://ip-10-0-0-111.eu-west-1.compute.internal:8088/proxy/application_1489137140207_0003/
    17/03/10 09:44:30 INFO mapreduce.Job: Running job: job_1489137140207_0003
    17/03/10 09:44:36 INFO mapreduce.Job: Job job_1489137140207_0003 running in uber mode : false
    17/03/10 09:44:36 INFO mapreduce.Job:  map 0% reduce 0%
    17/03/10 09:44:53 INFO mapreduce.Job:  map 17% reduce 0%
    17/03/10 09:44:57 INFO mapreduce.Job:  map 24% reduce 0%
    17/03/10 09:44:58 INFO mapreduce.Job:  map 26% reduce 0%
    17/03/10 09:44:59 INFO mapreduce.Job:  map 29% reduce 0%
    17/03/10 09:45:03 INFO mapreduce.Job:  map 32% reduce 0%
    17/03/10 09:45:05 INFO mapreduce.Job:  map 36% reduce 0%
    17/03/10 09:45:08 INFO mapreduce.Job:  map 37% reduce 0%
    17/03/10 09:45:09 INFO mapreduce.Job:  map 38% reduce 0%
    17/03/10 09:45:10 INFO mapreduce.Job:  map 39% reduce 0%
    17/03/10 09:45:11 INFO mapreduce.Job:  map 43% reduce 0%
    17/03/10 09:45:15 INFO mapreduce.Job:  map 44% reduce 0%
    17/03/10 09:45:16 INFO mapreduce.Job:  map 46% reduce 0%
    17/03/10 09:45:18 INFO mapreduce.Job:  map 50% reduce 0%
    17/03/10 09:45:21 INFO mapreduce.Job:  map 51% reduce 0%
    17/03/10 09:45:22 INFO mapreduce.Job:  map 52% reduce 0%
    17/03/10 09:45:23 INFO mapreduce.Job:  map 53% reduce 0%
    17/03/10 09:45:24 INFO mapreduce.Job:  map 57% reduce 0%
    17/03/10 09:45:27 INFO mapreduce.Job:  map 58% reduce 0%
    17/03/10 09:45:28 INFO mapreduce.Job:  map 60% reduce 0%
    17/03/10 09:45:30 INFO mapreduce.Job:  map 64% reduce 0%
    17/03/10 09:45:33 INFO mapreduce.Job:  map 66% reduce 0%
    17/03/10 09:45:34 INFO mapreduce.Job:  map 67% reduce 0%
    17/03/10 09:45:36 INFO mapreduce.Job:  map 71% reduce 0%
    17/03/10 09:45:39 INFO mapreduce.Job:  map 73% reduce 0%
    17/03/10 09:45:40 INFO mapreduce.Job:  map 75% reduce 0%
    17/03/10 09:45:42 INFO mapreduce.Job:  map 78% reduce 0%
    17/03/10 09:45:45 INFO mapreduce.Job:  map 80% reduce 0%
    17/03/10 09:45:46 INFO mapreduce.Job:  map 82% reduce 0%
    17/03/10 09:45:48 INFO mapreduce.Job:  map 85% reduce 0%
    17/03/10 09:45:51 INFO mapreduce.Job:  map 87% reduce 0%
    17/03/10 09:45:52 INFO mapreduce.Job:  map 89% reduce 0%
    17/03/10 09:45:53 INFO mapreduce.Job:  map 90% reduce 0%
    17/03/10 09:45:54 INFO mapreduce.Job:  map 91% reduce 0%
    17/03/10 09:45:57 INFO mapreduce.Job:  map 93% reduce 0%
    17/03/10 09:46:03 INFO mapreduce.Job:  map 96% reduce 0%
    17/03/10 09:46:04 INFO mapreduce.Job:  map 98% reduce 0%
    17/03/10 09:46:06 INFO mapreduce.Job:  map 100% reduce 0%
    17/03/10 09:46:06 INFO mapreduce.Job: Job job_1489137140207_0003 completed successfully
    17/03/10 09:46:06 INFO mapreduce.Job: Counters: 31
      File System Counters
        FILE: Number of bytes read=0
        FILE: Number of bytes written=997616
        FILE: Number of read operations=0
        FILE: Number of large read operations=0
        FILE: Number of write operations=0
        HDFS: Number of bytes read=682
        HDFS: Number of bytes written=6553600000
        HDFS: Number of read operations=32
        HDFS: Number of large read operations=0
        HDFS: Number of write operations=16
      Job Counters
        Launched map tasks=8
        Other local map tasks=8
        Total time spent by all maps in occupied slots (ms)=653914
        Total time spent by all reduces in occupied slots (ms)=0
        Total time spent by all map tasks (ms)=653914
        Total vcore-seconds taken by all map tasks=653914
        Total megabyte-seconds taken by all map tasks=669607936
      Map-Reduce Framework
        Map input records=65536000
        Map output records=65536000
        Input split bytes=682
        Spilled Records=0
        Failed Shuffles=0
        Merged Map outputs=0
        GC time elapsed (ms)=1917
        CPU time spent (ms)=126400
        Physical memory (bytes) snapshot=2912182272
        Virtual memory (bytes) snapshot=22294454272
        Total committed heap usage (bytes)=2742550528
      org.apache.hadoop.examples.terasort.TeraGen$Counters
        CHECKSUM=140750829423462787
      File Input Format Counters
        Bytes Read=0
      File Output Format Counters
        Bytes Written=6553600000

    real  1m40.189s
    user  0m8.828s
    sys 0m0.410s
    ```

2. Time:

  ```
    real  1m55.217s
    user  0m8.626s
    sys 0m0.442s
  ```

3. The command and output of hdfs dfs -ls /user/neymar/tgen640

    ```
      [neymar@ip-10-0-0-111 ~]$ hdfs dfs -ls /user/neymar/tgen640
      Found 9 items
      -rw-r--r--   3 neymar neymar          0 2017-03-10 09:46 /user/neymar/tgen640/_SUCCESS
      -rw-r--r--   3 neymar neymar  819200000 2017-03-10 09:46 /user/neymar/tgen640/part-m-00000
      -rw-r--r--   3 neymar neymar  819200000 2017-03-10 09:46 /user/neymar/tgen640/part-m-00001
      -rw-r--r--   3 neymar neymar  819200000 2017-03-10 09:46 /user/neymar/tgen640/part-m-00002
      -rw-r--r--   3 neymar neymar  819200000 2017-03-10 09:45 /user/neymar/tgen640/part-m-00003
      -rw-r--r--   3 neymar neymar  819200000 2017-03-10 09:45 /user/neymar/tgen640/part-m-00004
      -rw-r--r--   3 neymar neymar  819200000 2017-03-10 09:45 /user/neymar/tgen640/part-m-00005
      -rw-r--r--   3 neymar neymar  819200000 2017-03-10 09:45 /user/neymar/tgen640/part-m-00006
      -rw-r--r--   3 neymar neymar  819200000 2017-03-10 09:46 /user/neymar/tgen640/part-m-00007
      ```

4. The command and output to show how many blocks are stored under this directory

  ```
    [neymar@ip-10-0-0-111 ~]$ hdfs fsck /user/neymar/tgen640/
    Connecting to namenode via http://ip-10-0-0-111.eu-west-1.compute.internal:50070
    FSCK started by neymar (auth:SIMPLE) from /10.0.0.111 for path /user/neymar/tgen640/ at Fri Mar 10 09:48:13 UTC 2017
    .........Status: HEALTHY
     Total size:  6553600000 B
     Total dirs:  1
     Total files: 9
     Total symlinks:    0
     Total blocks (validated):  392 (avg. block size 16718367 B)
     Minimally replicated blocks: 392 (100.0 %)
     Over-replicated blocks:  0 (0.0 %)
     Under-replicated blocks: 0 (0.0 %)
     Mis-replicated blocks:   0 (0.0 %)
     Default replication factor:  3
     Average block replication: 3.0
     Corrupt blocks:    0
     Missing replicas:    0 (0.0 %)
     Number of data-nodes:    3
     Number of racks:   1
    FSCK ended at Fri Mar 10 09:48:13 UTC 2017 in 4 milliseconds


    The filesystem under path '/user/neymar/tgen640/' is HEALTHY
  ```

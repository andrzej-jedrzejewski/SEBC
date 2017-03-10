1. 

  ```
    kdestroy
    kdestroy: No credentials cache found while destroying cache
    [neymar@ip-10-0-0-111 ~]$ kinit
    Password for neymar@ANDRZEJJEDRZEJEWSKI.ES:
    [neymar@ip-10-0-0-111 ~]$
    [neymar@ip-10-0-0-111 ~]$ klist
    Ticket cache: FILE:/tmp/krb5cc_2010
    Default principal: neymar@ANDRZEJJEDRZEJEWSKI.ES

    Valid starting       Expires              Service principal
    03/10/2017 10:13:25  03/11/2017 10:13:25  krbtgt/ANDRZEJJEDRZEJEWSKI.ES@ANDRZEJJEDRZEJEWSKI.ES
      renew until 03/17/2017 10:13:25
    ```

2.  
  ```     
    [neymar@ip-10-0-0-111 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort -Dmapred.map.tasks=8 /user/neymar/tgen640 /user/neymar/tsort640m
    17/03/10 10:15:39 INFO terasort.TeraSort: starting
    17/03/10 10:15:40 INFO hdfs.DFSClient: Created token for neymar: HDFS_DELEGATION_TOKEN owner=neymar@ANDRZEJJEDRZEJEWSKI.ES, renewer=yarn, realUser=, issueDate=1489140940530, maxDate=1489745740530, sequenceNumber=1, masterKeyId=2 on 10.0.0.111:8020
    17/03/10 10:15:40 INFO security.TokenCache: Got dt for hdfs://ip-10-0-0-111.eu-west-1.compute.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 10.0.0.111:8020, Ident: (token for neymar: HDFS_DELEGATION_TOKEN owner=neymar@ANDRZEJJEDRZEJEWSKI.ES, renewer=yarn, realUser=, issueDate=1489140940530, maxDate=1489745740530, sequenceNumber=1, masterKeyId=2)
    17/03/10 10:15:40 INFO input.FileInputFormat: Total input paths to process : 8
    Spent 465ms computing base-splits.
    Spent 9ms computing TeraScheduler splits.
    Computing input splits took 475ms
    Sampling 10 splits of 392
    Making 6 from 100000 sampled records
    Computing parititions took 810ms
    Spent 1287ms computing partitions.
    17/03/10 10:15:41 INFO client.RMProxy: Connecting to ResourceManager at ip-10-0-0-111.eu-west-1.compute.internal/10.0.0.111:8032
    17/03/10 10:15:42 INFO mapreduce.JobSubmitter: number of splits:392
    17/03/10 10:15:42 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
    17/03/10 10:15:42 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1489140626231_0001
    17/03/10 10:15:42 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 10.0.0.111:8020, Ident: (token for neymar: HDFS_DELEGATION_TOKEN owner=neymar@ANDRZEJJEDRZEJEWSKI.ES, renewer=yarn, realUser=, issueDate=1489140940530, maxDate=1489745740530, sequenceNumber=1, masterKeyId=2)
    17/03/10 10:15:43 INFO impl.YarnClientImpl: Submitted application application_1489140626231_0001
    17/03/10 10:15:43 INFO mapreduce.Job: The url to track the job: http://ip-10-0-0-111.eu-west-1.compute.internal:8088/proxy/application_1489140626231_0001/
    17/03/10 10:15:43 INFO mapreduce.Job: Running job: job_1489140626231_0001
    17/03/10 10:15:53 INFO mapreduce.Job: Job job_1489140626231_0001 running in uber mode : false
    17/03/10 10:15:53 INFO mapreduce.Job:  map 0% reduce 0%
    17/03/10 10:16:00 INFO mapreduce.Job:  map 1% reduce 0%
    17/03/10 10:16:11 INFO mapreduce.Job:  map 2% reduce 0%
    17/03/10 10:16:12 INFO mapreduce.Job:  map 3% reduce 0%
    17/03/10 10:16:13 INFO mapreduce.Job:  map 4% reduce 0%
    17/03/10 10:16:22 INFO mapreduce.Job:  map 5% reduce 0%
    17/03/10 10:16:23 INFO mapreduce.Job:  map 6% reduce 0%
    17/03/10 10:16:25 INFO mapreduce.Job:  map 7% reduce 0%
    17/03/10 10:16:33 INFO mapreduce.Job:  map 8% reduce 0%
    17/03/10 10:16:34 INFO mapreduce.Job:  map 9% reduce 0%
    17/03/10 10:16:37 INFO mapreduce.Job:  map 10% reduce 0%
    17/03/10 10:16:44 INFO mapreduce.Job:  map 11% reduce 0%
    17/03/10 10:16:45 INFO mapreduce.Job:  map 12% reduce 0%
    17/03/10 10:16:49 INFO mapreduce.Job:  map 13% reduce 0%
    17/03/10 10:16:54 INFO mapreduce.Job:  map 14% reduce 0%
    17/03/10 10:16:57 INFO mapreduce.Job:  map 15% reduce 0%
    17/03/10 10:17:00 INFO mapreduce.Job:  map 16% reduce 0%
    17/03/10 10:17:05 INFO mapreduce.Job:  map 17% reduce 0%
    17/03/10 10:17:08 INFO mapreduce.Job:  map 18% reduce 0%
    17/03/10 10:17:12 INFO mapreduce.Job:  map 19% reduce 0%
    17/03/10 10:17:16 INFO mapreduce.Job:  map 20% reduce 0%
    17/03/10 10:17:18 INFO mapreduce.Job:  map 21% reduce 0%
    17/03/10 10:17:24 INFO mapreduce.Job:  map 22% reduce 0%
    17/03/10 10:17:26 INFO mapreduce.Job:  map 23% reduce 0%
    17/03/10 10:17:29 INFO mapreduce.Job:  map 24% reduce 0%
    17/03/10 10:17:34 INFO mapreduce.Job:  map 25% reduce 0%
    17/03/10 10:17:36 INFO mapreduce.Job:  map 26% reduce 0%
    17/03/10 10:17:39 INFO mapreduce.Job:  map 27% reduce 0%
    17/03/10 10:17:44 INFO mapreduce.Job:  map 28% reduce 0%
    17/03/10 10:17:46 INFO mapreduce.Job:  map 29% reduce 0%
    17/03/10 10:17:50 INFO mapreduce.Job:  map 30% reduce 0%
    17/03/10 10:17:54 INFO mapreduce.Job:  map 31% reduce 0%
    17/03/10 10:17:56 INFO mapreduce.Job:  map 32% reduce 0%
    17/03/10 10:18:03 INFO mapreduce.Job:  map 33% reduce 0%
    17/03/10 10:18:05 INFO mapreduce.Job:  map 34% reduce 0%
    17/03/10 10:18:10 INFO mapreduce.Job:  map 35% reduce 0%
    17/03/10 10:18:13 INFO mapreduce.Job:  map 36% reduce 0%
    17/03/10 10:18:16 INFO mapreduce.Job:  map 37% reduce 0%
    17/03/10 10:18:18 INFO mapreduce.Job:  map 38% reduce 0%
    17/03/10 10:18:23 INFO mapreduce.Job:  map 39% reduce 0%
    17/03/10 10:18:25 INFO mapreduce.Job:  map 40% reduce 0%
    17/03/10 10:18:29 INFO mapreduce.Job:  map 41% reduce 0%
    17/03/10 10:18:34 INFO mapreduce.Job:  map 42% reduce 0%
    17/03/10 10:18:35 INFO mapreduce.Job:  map 43% reduce 0%
    17/03/10 10:18:41 INFO mapreduce.Job:  map 44% reduce 0%
    17/03/10 10:18:45 INFO mapreduce.Job:  map 45% reduce 0%
    17/03/10 10:18:47 INFO mapreduce.Job:  map 46% reduce 0%
    17/03/10 10:18:52 INFO mapreduce.Job:  map 47% reduce 0%
    17/03/10 10:18:56 INFO mapreduce.Job:  map 48% reduce 0%
    17/03/10 10:18:58 INFO mapreduce.Job:  map 49% reduce 0%
    17/03/10 10:19:04 INFO mapreduce.Job:  map 50% reduce 0%
    17/03/10 10:19:05 INFO mapreduce.Job:  map 51% reduce 0%
    17/03/10 10:19:07 INFO mapreduce.Job:  map 52% reduce 0%
    17/03/10 10:19:11 INFO mapreduce.Job:  map 53% reduce 0%
    17/03/10 10:19:16 INFO mapreduce.Job:  map 54% reduce 0%
    17/03/10 10:19:17 INFO mapreduce.Job:  map 55% reduce 0%
    17/03/10 10:19:23 INFO mapreduce.Job:  map 56% reduce 0%
    17/03/10 10:19:26 INFO mapreduce.Job:  map 57% reduce 0%
    17/03/10 10:19:29 INFO mapreduce.Job:  map 58% reduce 0%
    17/03/10 10:19:35 INFO mapreduce.Job:  map 59% reduce 0%
    17/03/10 10:19:37 INFO mapreduce.Job:  map 60% reduce 0%
    17/03/10 10:19:41 INFO mapreduce.Job:  map 61% reduce 0%
    17/03/10 10:19:46 INFO mapreduce.Job:  map 62% reduce 0%
    17/03/10 10:19:47 INFO mapreduce.Job:  map 63% reduce 0%
    17/03/10 10:19:52 INFO mapreduce.Job:  map 64% reduce 0%
    17/03/10 10:19:54 INFO mapreduce.Job:  map 65% reduce 0%
    17/03/10 10:19:59 INFO mapreduce.Job:  map 66% reduce 0%
    17/03/10 10:20:02 INFO mapreduce.Job:  map 67% reduce 0%
    17/03/10 10:20:06 INFO mapreduce.Job:  map 68% reduce 0%
    17/03/10 10:20:10 INFO mapreduce.Job:  map 69% reduce 0%
    17/03/10 10:20:12 INFO mapreduce.Job:  map 70% reduce 0%
    17/03/10 10:20:17 INFO mapreduce.Job:  map 71% reduce 0%
    17/03/10 10:20:20 INFO mapreduce.Job:  map 72% reduce 0%
    17/03/10 10:20:22 INFO mapreduce.Job:  map 73% reduce 0%
    17/03/10 10:20:29 INFO mapreduce.Job:  map 74% reduce 0%
    17/03/10 10:20:30 INFO mapreduce.Job:  map 75% reduce 0%
    17/03/10 10:20:33 INFO mapreduce.Job:  map 76% reduce 0%
    17/03/10 10:20:39 INFO mapreduce.Job:  map 77% reduce 0%
    17/03/10 10:20:41 INFO mapreduce.Job:  map 78% reduce 0%
    17/03/10 10:20:43 INFO mapreduce.Job:  map 79% reduce 0%
    17/03/10 10:20:49 INFO mapreduce.Job:  map 80% reduce 0%
    17/03/10 10:20:52 INFO mapreduce.Job:  map 81% reduce 0%
    17/03/10 10:20:54 INFO mapreduce.Job:  map 82% reduce 0%
    17/03/10 10:21:00 INFO mapreduce.Job:  map 83% reduce 0%
    17/03/10 10:21:10 INFO mapreduce.Job:  map 84% reduce 5%
    17/03/10 10:21:13 INFO mapreduce.Job:  map 85% reduce 9%
    17/03/10 10:21:14 INFO mapreduce.Job:  map 85% reduce 13%
    17/03/10 10:21:16 INFO mapreduce.Job:  map 85% reduce 22%
    17/03/10 10:21:20 INFO mapreduce.Job:  map 85% reduce 23%
    17/03/10 10:21:22 INFO mapreduce.Job:  map 85% reduce 24%
    17/03/10 10:21:23 INFO mapreduce.Job:  map 86% reduce 24%
    17/03/10 10:21:28 INFO mapreduce.Job:  map 87% reduce 24%
    17/03/10 10:21:34 INFO mapreduce.Job:  map 88% reduce 24%
    17/03/10 10:21:40 INFO mapreduce.Job:  map 89% reduce 24%
    17/03/10 10:21:41 INFO mapreduce.Job:  map 89% reduce 25%
    17/03/10 10:21:46 INFO mapreduce.Job:  map 90% reduce 25%
    17/03/10 10:21:52 INFO mapreduce.Job:  map 91% reduce 25%
    17/03/10 10:21:56 INFO mapreduce.Job:  map 92% reduce 25%
    17/03/10 10:22:02 INFO mapreduce.Job:  map 93% reduce 25%
    17/03/10 10:22:04 INFO mapreduce.Job:  map 93% reduce 26%
    17/03/10 10:22:09 INFO mapreduce.Job:  map 94% reduce 26%
    17/03/10 10:22:13 INFO mapreduce.Job:  map 95% reduce 26%
    17/03/10 10:22:20 INFO mapreduce.Job:  map 96% reduce 26%
    17/03/10 10:22:23 INFO mapreduce.Job:  map 96% reduce 27%
    17/03/10 10:22:27 INFO mapreduce.Job:  map 97% reduce 27%
    17/03/10 10:22:33 INFO mapreduce.Job:  map 98% reduce 27%
    17/03/10 10:22:39 INFO mapreduce.Job:  map 99% reduce 27%
    17/03/10 10:22:43 INFO mapreduce.Job:  map 100% reduce 27%
    17/03/10 10:22:44 INFO mapreduce.Job:  map 100% reduce 28%
    17/03/10 10:22:45 INFO mapreduce.Job:  map 100% reduce 33%
    17/03/10 10:22:46 INFO mapreduce.Job:  map 100% reduce 39%
    17/03/10 10:22:47 INFO mapreduce.Job:  map 100% reduce 50%
    17/03/10 10:22:50 INFO mapreduce.Job:  map 100% reduce 57%
    17/03/10 10:22:51 INFO mapreduce.Job:  map 100% reduce 59%
    17/03/10 10:22:52 INFO mapreduce.Job:  map 100% reduce 61%

    17/03/10 10:22:53 INFO mapreduce.Job:  map 100% reduce 66%
    17/03/10 10:22:56 INFO mapreduce.Job:  map 100% reduce 68%
    17/03/10 10:22:57 INFO mapreduce.Job:  map 100% reduce 76%
    17/03/10 10:22:58 INFO mapreduce.Job:  map 100% reduce 79%
    17/03/10 10:22:59 INFO mapreduce.Job:  map 100% reduce 85%
    17/03/10 10:23:01 INFO mapreduce.Job:  map 100% reduce 87%
    17/03/10 10:23:02 INFO mapreduce.Job:  map 100% reduce 89%
    17/03/10 10:23:03 INFO mapreduce.Job:  map 100% reduce 96%
    17/03/10 10:23:09 INFO mapreduce.Job:  map 100% reduce 99%
    17/03/10 10:23:11 INFO mapreduce.Job:  map 100% reduce 100%
    17/03/10 10:23:11 INFO mapreduce.Job: Job job_1489140626231_0001 completed successfully
    17/03/10 10:23:11 INFO mapreduce.Job: Counters: 49
      File System Counters
        FILE: Number of bytes read=2910851332
        FILE: Number of bytes written=5804593970
        FILE: Number of read operations=0
        FILE: Number of large read operations=0
        FILE: Number of write operations=0
        HDFS: Number of bytes read=6553658800
        HDFS: Number of bytes written=6553600000
        HDFS: Number of read operations=1194
        HDFS: Number of large read operations=0
        HDFS: Number of write operations=12
      Job Counters
        Launched map tasks=392
        Launched reduce tasks=6
        Data-local map tasks=392
        Total time spent by all maps in occupied slots (ms)=3023482
        Total time spent by all reduces in occupied slots (ms)=649906
        Total time spent by all map tasks (ms)=3023482
        Total time spent by all reduce tasks (ms)=649906
        Total vcore-seconds taken by all map tasks=3023482
        Total vcore-seconds taken by all reduce tasks=649906
        Total megabyte-seconds taken by all map tasks=3096045568
        Total megabyte-seconds taken by all reduce tasks=665503744
      Map-Reduce Framework
        Map input records=65536000
        Map output records=65536000
        Map output bytes=6684672000
        Map output materialized bytes=2843199072
        Input split bytes=58800
        Combine input records=0
        Combine output records=0
        Reduce input groups=65536000
        Reduce shuffle bytes=2843199072
        Reduce input records=65536000
        Reduce output records=65536000
        Spilled Records=131072000
        Shuffled Maps =2352
        Failed Shuffles=0
        Merged Map outputs=2352
        GC time elapsed (ms)=67919
        CPU time spent (ms)=1502280
        Physical memory (bytes) snapshot=192429408256
        Virtual memory (bytes) snapshot=1109864837120
        Total committed heap usage (bytes)=195821043712
      Shuffle Errors
        BAD_ID=0
        CONNECTION=0
        IO_ERROR=0
        WRONG_LENGTH=0
        WRONG_MAP=0
        WRONG_REDUCE=0
      File Input Format Counters
        Bytes Read=6553600000
      File Output Format Counters
        Bytes Written=6553600000
    17/03/10 10:23:11 INFO terasort.TeraSort: done

    real  7m33.817s
    user  0m12.344s
    sys 0m0.531s
    ```
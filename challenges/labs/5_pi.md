1. Command and output for pi example
  ```
    [ronaldo@ip-10-0-0-111 ~]$ kinit
    Password for ronaldo@ANDRZEJJEDRZEJEWSKI.ES:
    [ronaldo@ip-10-0-0-111 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar pi 16 1000000
    Number of Maps  = 16
    Samples per Map = 1000000
    Wrote input for Map #0
    Wrote input for Map #1
    Wrote input for Map #2
    Wrote input for Map #3
    Wrote input for Map #4
    Wrote input for Map #5
    Wrote input for Map #6
    Wrote input for Map #7
    Wrote input for Map #8
    Wrote input for Map #9
    Wrote input for Map #10
    Wrote input for Map #11
    Wrote input for Map #12
    Wrote input for Map #13
    Wrote input for Map #14
    Wrote input for Map #15
    Starting Job
    17/03/10 10:35:03 INFO client.RMProxy: Connecting to ResourceManager at ip-10-0-0-111.eu-west-1.compute.internal/10.0.0.111:8032
    17/03/10 10:35:03 INFO hdfs.DFSClient: Created token for ronaldo: HDFS_DELEGATION_TOKEN owner=ronaldo@ANDRZEJJEDRZEJEWSKI.ES, renewer=yarn, realUser=, issueDate=1489142103910, maxDate=1489746903910, sequenceNumber=2, masterKeyId=2 on 10.0.0.111:8020
    17/03/10 10:35:03 INFO security.TokenCache: Got dt for hdfs://ip-10-0-0-111.eu-west-1.compute.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 10.0.0.111:8020, Ident: (token for ronaldo: HDFS_DELEGATION_TOKEN owner=ronaldo@ANDRZEJJEDRZEJEWSKI.ES, renewer=yarn, realUser=, issueDate=1489142103910, maxDate=1489746903910, sequenceNumber=2, masterKeyId=2)
    17/03/10 10:35:04 INFO input.FileInputFormat: Total input paths to process : 16
    17/03/10 10:35:04 INFO mapreduce.JobSubmitter: number of splits:16
    17/03/10 10:35:04 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1489140626231_0002
    17/03/10 10:35:04 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 10.0.0.111:8020, Ident: (token for ronaldo: HDFS_DELEGATION_TOKEN owner=ronaldo@ANDRZEJJEDRZEJEWSKI.ES, renewer=yarn, realUser=, issueDate=1489142103910, maxDate=1489746903910, sequenceNumber=2, masterKeyId=2)
    17/03/10 10:35:05 INFO impl.YarnClientImpl: Submitted application application_1489140626231_0002
    17/03/10 10:35:05 INFO mapreduce.Job: The url to track the job: http://ip-10-0-0-111.eu-west-1.compute.internal:8088/proxy/application_1489140626231_0002/
    17/03/10 10:35:05 INFO mapreduce.Job: Running job: job_1489140626231_0002
    17/03/10 10:35:13 INFO mapreduce.Job: Job job_1489140626231_0002 running in uber mode : false
    17/03/10 10:35:13 INFO mapreduce.Job:  map 0% reduce 0%
    17/03/10 10:35:21 INFO mapreduce.Job:  map 13% reduce 0%
    17/03/10 10:35:22 INFO mapreduce.Job:  map 19% reduce 0%
    17/03/10 10:35:25 INFO mapreduce.Job:  map 38% reduce 0%
    17/03/10 10:35:27 INFO mapreduce.Job:  map 50% reduce 0%
    17/03/10 10:35:28 INFO mapreduce.Job:  map 81% reduce 0%
    17/03/10 10:35:32 INFO mapreduce.Job:  map 100% reduce 0%
    17/03/10 10:35:34 INFO mapreduce.Job:  map 100% reduce 100%
    17/03/10 10:35:34 INFO mapreduce.Job: Job job_1489140626231_0002 completed successfully
    17/03/10 10:35:34 INFO mapreduce.Job: Counters: 49
      File System Counters
        FILE: Number of bytes read=174
        FILE: Number of bytes written=2146271
        FILE: Number of read operations=0
        FILE: Number of large read operations=0
        FILE: Number of write operations=0
        HDFS: Number of bytes read=4758
        HDFS: Number of bytes written=215
        HDFS: Number of read operations=67
        HDFS: Number of large read operations=0
        HDFS: Number of write operations=3
      Job Counters
        Launched map tasks=16
        Launched reduce tasks=1
        Data-local map tasks=16
        Total time spent by all maps in occupied slots (ms)=132852
        Total time spent by all reduces in occupied slots (ms)=2936
        Total time spent by all map tasks (ms)=132852
        Total time spent by all reduce tasks (ms)=2936
        Total vcore-seconds taken by all map tasks=132852
        Total vcore-seconds taken by all reduce tasks=2936
        Total megabyte-seconds taken by all map tasks=136040448
        Total megabyte-seconds taken by all reduce tasks=3006464
      Map-Reduce Framework
        Map input records=16
        Map output records=32
        Map output bytes=288
        Map output materialized bytes=576
        Input split bytes=2870
        Combine input records=0
        Combine output records=0
        Reduce input groups=2
        Reduce shuffle bytes=576
        Reduce input records=32
        Reduce output records=0
        Spilled Records=64
        Shuffled Maps =16
        Failed Shuffles=0
        Merged Map outputs=16
        GC time elapsed (ms)=2577
        CPU time spent (ms)=15930
        Physical memory (bytes) snapshot=7493750784
        Virtual memory (bytes) snapshot=47402123264
        Total committed heap usage (bytes)=7894728704
      Shuffle Errors
        BAD_ID=0
        CONNECTION=0
        IO_ERROR=0
        WRONG_LENGTH=0
        WRONG_MAP=0
        WRONG_REDUCE=0
      File Input Format Counters
        Bytes Read=1888
      File Output Format Counters
        Bytes Written=97
    Job Finished in 31.15 seconds
    Estimated value of Pi is 3.14159125000000000000

    real  0m34.507s
    user  0m8.771s
    sys 0m0.422s
  ```
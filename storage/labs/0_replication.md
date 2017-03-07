1. Distcp replication. I generated test file with following command:
    ```
    hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapred.map.tasks=1 -Dmapred.map.tasks.speculative.execution=false 5242880 /data/andrzej-jedrzejewski
    ```
    The same thing was done on second cluster but with */data/gerardovazquez*

    To copy data between cluster:

    ```
    hadoop distcp webhdfs://34.252.56.113/data/gerardovazquez hdfs://ip-10-0-0-206.eu-west-1.compute.internal/data/gerardovazquez
    ```
    34.252.56.113 - source (gerardovazquez)
    ip-10-0-0-206.eu-west-1.compute.internal - target (andrzej-jedrzejewski)

    I encountered a problem with internal dns name resolution. To solve that I added in target cluster:
    ```
    34.250.173.172  ip-10-0-0-206.eu-west-1.compute.internal
    34.250.134.251  ip-10-0-0-106.eu-west-1.compute.internal
    34.249.155.8  ip-10-0-0-149.eu-west-1.compute.internal
    34.250.246.51  ip-10-0-0-173.eu-west-1.compute.internal
    34.251.97.72  ip-10-0-0-93.eu-west-1.compute.internal
    ```
    After that I was able to copy data from source cluster to target one:
    ```
    hadoop distcp webhdfs://34.252.56.113/data/gerardovazquez hdfs://ip-10-0-0-206.eu-west-1.compute.internal/data/gerardovazquez
    17/03/07 11:04:26 INFO tools.DistCp: Input Options: DistCpOptions{atomicCommit=false, syncFolder=false, deleteMissing=false, ignoreFailures=false, overwrite=false, append=false, useDiff=false, useRdiff=false, fromSnapshot=null, toSnapshot=null, skipCRC=false, blocking=true, numListstatusThreads=0, maxMaps=20, mapBandwidth=100, sslConfigurationFile='null', copyStrategy='uniformsize', preserveStatus=[], preserveRawXattrs=false, atomicWorkPath=null, logPath=null, sourceFileListing=null, sourcePaths=[webhdfs://34.252.56.113/data/gerardovazquez], targetPath=hdfs://ip-10-0-0-206.eu-west-1.compute.internal/data/gerardovazquez, targetPathExists=true, filtersFile='null'}
    17/03/07 11:04:26 INFO Configuration.deprecation: session.id is deprecated. Instead, use dfs.metrics.session-id
    17/03/07 11:04:26 INFO jvm.JvmMetrics: Initializing JVM Metrics with processName=JobTracker, sessionId=
    17/03/07 11:04:27 INFO tools.SimpleCopyListing: Paths (files+dirs) cnt = 3; dirCnt = 1
    17/03/07 11:04:27 INFO tools.SimpleCopyListing: Build file listing completed.
    17/03/07 11:04:27 INFO Configuration.deprecation: io.sort.mb is deprecated. Instead, use mapreduce.task.io.sort.mb
    17/03/07 11:04:27 INFO Configuration.deprecation: io.sort.factor is deprecated. Instead, use mapreduce.task.io.sort.factor
    17/03/07 11:04:27 INFO tools.DistCp: Number of paths in the copy list: 3
    17/03/07 11:04:27 INFO tools.DistCp: Number of paths in the copy list: 3
    17/03/07 11:04:27 INFO jvm.JvmMetrics: Cannot initialize JVM Metrics with processName=JobTracker, sessionId= - already initialized
    17/03/07 11:04:27 INFO mapreduce.JobSubmitter: number of splits:1
    17/03/07 11:04:27 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_local648768914_0001
    17/03/07 11:04:27 INFO mapreduce.Job: The url to track the job: http://localhost:8080/
    17/03/07 11:04:27 INFO tools.DistCp: DistCp job-id: job_local648768914_0001
    17/03/07 11:04:27 INFO mapreduce.Job: Running job: job_local648768914_0001
    17/03/07 11:04:27 INFO mapred.LocalJobRunner: OutputCommitter set in config null
    17/03/07 11:04:27 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
    17/03/07 11:04:27 INFO mapred.LocalJobRunner: OutputCommitter is org.apache.hadoop.tools.mapred.CopyCommitter
    17/03/07 11:04:27 INFO mapred.LocalJobRunner: Waiting for map tasks
    17/03/07 11:04:27 INFO mapred.LocalJobRunner: Starting task: attempt_local648768914_0001_m_000000_0
    17/03/07 11:04:27 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
    17/03/07 11:04:27 INFO mapred.Task: Using ResourceCalculatorProcessTree : [ ]
    17/03/07 11:04:27 INFO mapred.MapTask: Processing split: file:/tmp/hadoop-root/mapred/staging/root396307406/.staging/_distcp-1599912931/fileList.seq:0+593
    17/03/07 11:04:27 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
    17/03/07 11:04:28 INFO mapred.CopyMapper: Copying webhdfs://34.252.56.113/data/gerardovazquez to hdfs://ip-10-0-0-206.eu-west-1.compute.internal/data/gerardovazquez/gerardovazquez
    17/03/07 11:04:28 INFO mapred.CopyMapper: Copying webhdfs://34.252.56.113/data/gerardovazquez/_SUCCESS to hdfs://ip-10-0-0-206.eu-west-1.compute.internal/data/gerardovazquez/gerardovazquez/_SUCCESS
    17/03/07 11:04:28 INFO mapred.CopyMapper: Skipping copy of webhdfs://34.252.56.113/data/gerardovazquez/_SUCCESS to hdfs://ip-10-0-0-206.eu-west-1.compute.internal/data/gerardovazquez/gerardovazquez/_SUCCESS
    17/03/07 11:04:28 INFO mapred.CopyMapper: Copying webhdfs://34.252.56.113/data/gerardovazquez/part-m-00000 to hdfs://ip-10-0-0-206.eu-west-1.compute.internal/data/gerardovazquez/gerardovazquez/part-m-00000
    17/03/07 11:04:28 INFO mapred.RetriableFileCopyCommand: Creating temp file: hdfs://ip-10-0-0-206.eu-west-1.compute.internal/data/gerardovazquez/.distcp.tmp.attempt_local648768914_0001_m_000000_0
    17/03/07 11:04:28 INFO mapreduce.Job: Job job_local648768914_0001 running in uber mode : false
    17/03/07 11:04:28 INFO mapreduce.Job: map 0% reduce 0%
    17/03/07 11:04:33 INFO mapred.LocalJobRunner: 77.8% Copying webhdfs://34.252.56.113/data/gerardovazquez/part-m-00000 to hdfs://ip-10-0-0-206.eu-west-1.compute.internal/data/gerardovazquez/gerardovazquez/part-m-00000 [388.9M/500.0M] > map
    17/03/07 11:04:34 INFO mapreduce.Job: map 100% reduce 0%
    17/03/07 11:04:36 INFO mapred.LocalJobRunner: 77.8% Copying webhdfs://34.252.56.113/data/gerardovazquez/part-m-00000 to hdfs://ip-10-0-0-206.eu-west-1.compute.internal/data/gerardovazquez/gerardovazquez/part-m-00000 [388.9M/500.0M] > map
    17/03/07 11:04:36 INFO mapred.Task: Task:attempt_local648768914_0001_m_000000_0 is done. And is in the process of committing
    17/03/07 11:04:36 INFO mapred.LocalJobRunner: 77.8% Copying webhdfs://34.252.56.113/data/gerardovazquez/part-m-00000 to hdfs://ip-10-0-0-206.eu-west-1.compute.internal/data/gerardovazquez/gerardovazquez/part-m-00000 [388.9M/500.0M] > map
    17/03/07 11:04:36 INFO mapred.Task: Task attempt_local648768914_0001_m_000000_0 is allowed to commit now
    17/03/07 11:04:36 INFO output.FileOutputCommitter: Saved output of task 'attempt_local648768914_0001_m_000000_0' to file:/tmp/hadoop-root/mapred/staging/root396307406/.staging/_distcp-1599912931/_logs/_temporary/0/task_local648768914_0001_m_000000
    17/03/07 11:04:36 INFO mapred.LocalJobRunner: 100.0% Copying webhdfs://34.252.56.113/data/gerardovazquez/part-m-00000 to hdfs://ip-10-0-0-206.eu-west-1.compute.internal/data/gerardovazquez/gerardovazquez/part-m-00000 [500.0M/500.0M]
    17/03/07 11:04:36 INFO mapred.Task: Task 'attempt_local648768914_0001_m_000000_0' done.
    17/03/07 11:04:36 INFO mapred.LocalJobRunner: Finishing task: attempt_local648768914_0001_m_000000_0
    17/03/07 11:04:36 INFO mapred.LocalJobRunner: map task executor complete.
    17/03/07 11:04:36 INFO mapred.CopyCommitter: Cleaning up temporary work folder: file:/tmp/hadoop-root/mapred/staging/root396307406/.staging/_distcp-1599912931
    17/03/07 11:04:36 INFO mapreduce.Job: Job job_local648768914_0001 completed successfully
    17/03/07 11:04:36 INFO mapreduce.Job: Counters: 30
    File System Counters
    FILE: Number of bytes read=1959663
    FILE: Number of bytes written=2263476
    FILE: Number of read operations=0
    FILE: Number of large read operations=0
    FILE: Number of write operations=0
    HDFS: Number of bytes read=0
    HDFS: Number of bytes written=524288000
    HDFS: Number of read operations=15
    HDFS: Number of large read operations=0
    HDFS: Number of write operations=3
    WEBHDFS: Number of bytes read=524288000
    WEBHDFS: Number of bytes written=0
    WEBHDFS: Number of read operations=10
    WEBHDFS: Number of large read operations=0
    WEBHDFS: Number of write operations=0
    Map-Reduce Framework
    Map input records=3
    Map output records=1
    Input split bytes=156
    Spilled Records=0
    Failed Shuffles=0
    Merged Map outputs=0
    GC time elapsed (ms)=55
    Total committed heap usage (bytes)=177733632
    File Input Format Counters
    Bytes Read=629
    File Output Format Counters
    Bytes Written=71
    org.apache.hadoop.tools.mapred.CopyMapper$Counter
    BYTESCOPIED=524288000
    BYTESEXPECTED=524288000
    BYTESSKIPPED=0
    COPY=2
    SKIP=1
    ```
    To verify file:
    ```
    [andrzej-jedrzejewski@ip-10-0-0-206 ec2-user]$ hdfs fsck /data/gerardovazquez/gerardovazquez/part-m-00000 -files -blocks
    Connecting to namenode via http://ip-10-0-0-206.eu-west-1.compute.internal:50070
    FSCK started by andrzej-jedrzejewski (auth:SIMPLE) from /10.0.0.206 for path /data/gerardovazquez/gerardovazquez/part-m-00000 at Tue Mar 07 11:16:34 UTC 2017
    /data/gerardovazquez/gerardovazquez/part-m-00000 524288000 bytes, 4 block(s): OK
    0. BP-1373139715-10.0.0.206-1488832677861:blk_1073743338_2514 len=134217728 Live_repl=3
    BP-1373139715-10.0.0.206-1488832677861:blk_1073743339_2515 len=134217728 Live_repl=3
    BP-1373139715-10.0.0.206-1488832677861:blk_1073743341_2517 len=134217728 Live_repl=3
    BP-1373139715-10.0.0.206-1488832677861:blk_1073743342_2518 len=121634816 Live_repl=3
    Status: HEALTHY
    Total size: 524288000 B
    Total dirs: 0
    Total files:  1
    Total symlinks: 0
    Total blocks (validated): 4 (avg. block size 131072000 B)
    Minimally replicated blocks:  4 (100.0 %)
    Over-replicated blocks: 0 (0.0 %)
    Under-replicated blocks:  0 (0.0 %)
    Mis-replicated blocks:  0 (0.0 %)
    Default replication factor: 3
    Average block replication:  3.0
    Corrupt blocks: 0
    Missing replicas: 0 (0.0 %)
    Number of data-nodes: 3
    Number of racks:  1
    FSCK ended at Tue Mar 07 11:16:34 UTC 2017 in 1 milliseconds

    The filesystem under path '/data/gerardovazquez/gerardovazquez/part-m-00000' is HEALTHY
    ``` 

1. Teragen and terasort benchmark:

```
[andrzej-jedrzejewski@ip-10-0-0-206 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapred.map.tasks=4 -D dfs.block.size=33554432 -Dmapred.map.tasks.speculative.execution=false 100000000 /user/andrzej-jedrzejewski/terasort-input
```

```
17/03/07 13:26:40 INFO mapreduce.Job: Counters: 21
  File System Counters
    FILE: Number of bytes read=276330
    FILE: Number of bytes written=585925
    FILE: Number of read operations=0
    FILE: Number of large read operations=0
    FILE: Number of write operations=0
    HDFS: Number of bytes read=0
    HDFS: Number of bytes written=10000000000
    HDFS: Number of read operations=4
    HDFS: Number of large read operations=0
    HDFS: Number of write operations=3
  Map-Reduce Framework
    Map input records=100000000
    Map output records=100000000
    Input split bytes=83
    Spilled Records=0
    Failed Shuffles=0
    Merged Map outputs=0
    GC time elapsed (ms)=868
    Total committed heap usage (bytes)=180879360
  org.apache.hadoop.examples.terasort.TeraGen$Counters
    CHECKSUM=214760662691937609
  File Input Format Counters
    Bytes Read=0
  File Output Format Counters
    Bytes Written=10000000000

real  3m0.981s
```

```
time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort -Dmapred.map.tasks=4 /user/andrzej-jedrzejewski/terasort-input /user/andrzej-jedrzejewski/terasort-output
```

```
17/03/07 14:03:01 INFO mapreduce.Job: Counters: 35
  File System Counters
    FILE: Number of bytes read=31146081573
    FILE: Number of bytes written=1585975923024
    FILE: Number of read operations=0
    FILE: Number of large read operations=0
    FILE: Number of write operations=0
    HDFS: Number of bytes read=1508105708600
    HDFS: Number of bytes written=10000000000
    HDFS: Number of read operations=97176
    HDFS: Number of large read operations=0
    HDFS: Number of write operations=600
  Map-Reduce Framework
    Map input records=100000000
    Map output records=100000000
    Map output bytes=10200000000
    Map output materialized bytes=10400001788
    Input split bytes=50958
    Combine input records=0
    Combine output records=0
    Reduce input groups=100000000
    Reduce shuffle bytes=10400001788
    Reduce input records=100000000
    Reduce output records=100000000
    Spilled Records=296636764
    Shuffled Maps =298
    Failed Shuffles=0
    Merged Map outputs=298
    GC time elapsed (ms)=40232
    Total committed heap usage (bytes)=79522430976
  Shuffle Errors
    BAD_ID=0
    CONNECTION=0
    IO_ERROR=0
    WRONG_LENGTH=0
    WRONG_MAP=0
    WRONG_REDUCE=0
  File Input Format Counters
    Bytes Read=10000000000
  File Output Format Counters
    Bytes Written=10000000000
17/03/07 14:03:01 INFO terasort.TeraSort: done

real  12m54.889s
```


```
hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teravalidate -Dmapred.map.tasks=4 /user/andrzej-jedrzejewski/terasort-output /user/andrzej-jedrzejewski/terasort-validate
```
```
17/03/07 14:11:01 INFO mapreduce.Job: Counters: 35
  File System Counters
    FILE: Number of bytes read=553152
    FILE: Number of bytes written=1175069
    FILE: Number of read operations=0
    FILE: Number of large read operations=0
    FILE: Number of write operations=0
    HDFS: Number of bytes read=20000000000
    HDFS: Number of bytes written=25
    HDFS: Number of read operations=13
    HDFS: Number of large read operations=0
    HDFS: Number of write operations=4
  Map-Reduce Framework
    Map input records=100000000
    Map output records=3
    Map output bytes=83
    Map output materialized bytes=95
    Input split bytes=172
    Combine input records=0
    Combine output records=0
    Reduce input groups=3
    Reduce shuffle bytes=95
    Reduce input records=3
    Reduce output records=1
    Spilled Records=6
    Shuffled Maps =1
    Failed Shuffles=0
    Merged Map outputs=1
    GC time elapsed (ms)=672
    Total committed heap usage (bytes)=535822336
  Shuffle Errors
    BAD_ID=0
    CONNECTION=0
    IO_ERROR=0
    WRONG_LENGTH=0
    WRONG_MAP=0
    WRONG_REDUCE=0
  File Input Format Counters
    Bytes Read=10000000000
  File Output Format Counters
    Bytes Written=25

real  1m25.271s
```





```
hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapred.map.tasks=1 -Dmapred.map.tasks.speculative.execution=false 5000000 /user/andrzej-jedrzejewski/terasort-input
```

```
hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort /user/andrzej-jedrzejewski/terasort-input /user/andrzej-jedrzejewski/terasort-output
```

```
hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teravalidate /user/andrzej-jedrzejewski/terasort-output /user/andrzej-jedrzejewski/terasort-validate
```
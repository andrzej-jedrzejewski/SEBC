1. Change in in YARNCalcs:

    - OS CPU to 1
    - YARN vcores to 2 because final result was -1
    - spindels to 1

2. The Workload factor depends on worker's CPU and HDD and memory utilization

3. Parameters:
  ```
  yarn.nodemanager.resource.memory-mb is a total amount of physical memory for containers on WN.
  It should be = RAM – (RAM for OS + hadoop daemons + other services)
  ```

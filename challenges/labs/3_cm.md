1. Output of hdfs dfs -ls /user:

  ```
    [root@ip-10-0-0-111 yum.repos.d]# sudo -u hdfs hdfs dfs -ls /user/
    Found 6 items
    drwxrwxrwx   - mapred  hadoop           0 2017-03-10 09:12 /user/history
    drwxrwxr-t   - hive    hive             0 2017-03-10 09:12 /user/hive
    drwxrwxr-x   - hue     hue              0 2017-03-10 09:13 /user/hue
    drwxr-xr-x   - neymar  neymar           0 2017-03-10 09:16 /user/neymar
    drwxrwxr-x   - oozie   oozie            0 2017-03-10 09:13 /user/oozie
    drwxr-xr-x   - ronaldo ronaldo          0 2017-03-10 09:16 /user/ronaldo
  ```

3. Api call (hosts):

  ```json
        [root@ip-10-0-0-111 yum.repos.d]# curl -u admin:admin 'http://localhost:7180/api/v14/hosts'
    {
      "items" : [ {
        "hostId" : "124afb5b-d44e-42f3-aee7-ce079bdbdc96",
        "ipAddress" : "10.0.0.111",
        "hostname" : "ip-10-0-0-111.eu-west-1.compute.internal",
        "rackId" : "/default",
        "hostUrl" : "http://ip-10-0-0-111.eu-west-1.compute.internal:7180/cmf/hostRedirect/124afb5b-d44e-42f3-aee7-ce079bdbdc96",
        "maintenanceMode" : false,
        "maintenanceOwners" : [ ],
        "commissionState" : "COMMISSIONED",
        "numCores" : 4,
        "numPhysicalCores" : 2,
        "totalPhysMemBytes" : 15331930112
      }, {
        "hostId" : "060e7a94-ff11-4672-8f9b-8c4840e2489f",
        "ipAddress" : "10.0.0.175",
        "hostname" : "ip-10-0-0-175.eu-west-1.compute.internal",
        "rackId" : "/default",
        "hostUrl" : "http://ip-10-0-0-111.eu-west-1.compute.internal:7180/cmf/hostRedirect/060e7a94-ff11-4672-8f9b-8c4840e2489f",
        "maintenanceMode" : false,
        "maintenanceOwners" : [ ],
        "commissionState" : "COMMISSIONED",
        "numCores" : 4,
        "numPhysicalCores" : 2,
        "totalPhysMemBytes" : 15331930112
      }, {
        "hostId" : "3aa70f77-9e78-4ee5-a374-da95468afa61",
        "ipAddress" : "10.0.0.194",
        "hostname" : "ip-10-0-0-194.eu-west-1.compute.internal",
        "rackId" : "/default",
        "hostUrl" : "http://ip-10-0-0-111.eu-west-1.compute.internal:7180/cmf/hostRedirect/3aa70f77-9e78-4ee5-a374-da95468afa61",
        "maintenanceMode" : false,
        "maintenanceOwners" : [ ],
        "commissionState" : "COMMISSIONED",
        "numCores" : 4,
        "numPhysicalCores" : 2,
        "totalPhysMemBytes" : 15331930112
      }, {
        "hostId" : "e135288f-e94b-40cb-9f08-90958e803d52",
        "ipAddress" : "10.0.0.77",
        "hostname" : "ip-10-0-0-77.eu-west-1.compute.internal",
        "rackId" : "/default",
        "hostUrl" : "http://ip-10-0-0-111.eu-west-1.compute.internal:7180/cmf/hostRedirect/e135288f-e94b-40cb-9f08-90958e803d52",
        "maintenanceMode" : false,
        "maintenanceOwners" : [ ],
        "commissionState" : "COMMISSIONED",
        "numCores" : 4,
        "numPhysicalCores" : 2,
        "totalPhysMemBytes" : 15331930112
      }, {
        "hostId" : "dd92d76e-3523-48e2-b6bb-7da39ad88f03",
        "ipAddress" : "10.0.0.96",
        "hostname" : "ip-10-0-0-96.eu-west-1.compute.internal",
        "rackId" : "/default",
        "hostUrl" : "http://ip-10-0-0-111.eu-west-1.compute.internal:7180/cmf/hostRedirect/dd92d76e-3523-48e2-b6bb-7da39ad88f03",
        "maintenanceMode" : false,
        "maintenanceOwners" : [ ],
        "commissionState" : "COMMISSIONED",
        "numCores" : 4,
        "numPhysicalCores" : 2,
        "totalPhysMemBytes" : 15331930112
      } ]
    }
  ```
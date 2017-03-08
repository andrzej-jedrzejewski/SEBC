1. To check current state:

  ```json
  curl -u andrzej-jedrzejewski:cloudera 'http://localhost:7180/api/v13/clusters/andrzej-jedrzejewski/services/hive/'
  {
    "name" : "hive",
    "type" : "HIVE",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-10-0-0-206.eu-west-1.compute.internal:7180/cmf/serviceRedirect/hive",
    "roleInstancesUrl" : "http://ip-10-0-0-206.eu-west-1.compute.internal:7180/cmf/serviceRedirect/hive/instances",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "HIVE_HIVEMETASTORES_HEALTHY",
      "summary" : "GOOD",
      "suppressed" : false
    }, {
      "name" : "HIVE_HIVESERVER2S_HEALTHY",
      "summary" : "GOOD",
      "suppressed" : false
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Hive",
    "entityStatus" : "GOOD_HEALTH"
  }
  ```
2. To stop hive service:
  ```json
    curl -X POST -u andrzej-jedrzejewski:cloudera 'http://localhost:7180/api/v13/clusters/andrzej-jedrzejewski/services/hive/commands/stop'
  {
    "id" : 849,
    "name" : "Stop",
    "startTime" : "2017-03-08T11:28:48.467Z",
    "active" : true,
    "serviceRef" : {
      "clusterName" : "cluster",
      "serviceName" : "hive"
    }
  }
  ```
3. To start hive service:
  ```json
    curl -X POST -u andrzej-jedrzejewski:cloudera 'http://localhost:7180/api/v13/clusters/andrzej-jedrzejewski/services/hive/commands/start'
  {
    "id" : 853,
    "name" : "Start",
    "startTime" : "2017-03-08T11:33:12.582Z",
    "active" : true,
    "serviceRef" : {
      "clusterName" : "cluster",
      "serviceName" : "hive"
    }
  }
  ```





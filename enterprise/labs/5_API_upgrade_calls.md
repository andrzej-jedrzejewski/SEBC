1. Report the latest available version of the API
    ```json
    curl -X GET -u andrzej-jedrzejewski:cloudera 'http://localhost:7180/api/version'
    v14
    ```
2. Report the CM version
    ```json
     curl -X GET -u andrzej-jedrzejewski:cloudera 'http://localhost:7180/api/v14/cm/version'
      {
        "version" : "5.9.1",
        "buildUser" : "jenkins",
        "buildTimestamp" : "20170112-1158",
        "gitHash" : "a66d8bbdbe8bc3ee54235e55423f2f76c7d9f3b1",
        "snapshot" : false
      }
    ```
3. List all CM users
    ```json
      curl -X GET -u andrzej-jedrzejewski:cloudera 'http://localhost:7180/api/v14/users'
    {
      "items" : [ {
        "name" : "admin",
        "roles" : [ "ROLE_LIMITED" ]
      }, {
        "name" : "andrzej-jedrzejewski",
        "roles" : [ "ROLE_ADMIN" ]
      }, {
        "name" : "minotaur",
        "roles" : [ "ROLE_CONFIGURATOR" ]
      } ]
    ```
4. Report the database server in use by CM
    ```json
      curl -X GET -u andrzej-jedrzejewski:cloudera 'http://localhost:7180/api/v14/cm/scmDbInfo'
    {
      "scmDbType" : "MYSQL",
      "embeddedDbUsed" : false
    }
    ```
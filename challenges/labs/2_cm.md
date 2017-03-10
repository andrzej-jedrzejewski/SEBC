1. List the command and output for ls /etc/yum.repos.d

  ```
    [root@ip-10-0-0-111 yum.repos.d]# ls /etc/yum.repos.d
    redhat.repo  redhat-rhui-client-config.repo  redhat-rhui.repo  rhui-load-balancers.conf
  ```

2. Command

  ```
    /usr/share/cmf/schema/scm_prepare_database.sh -h ip-10-0-0-175.eu-west-1.compute.internal mysql scm scm ankara123
  ```

3. COmmand and output:

  ```
    [root@ip-10-0-0-111 yum.repos.d]# /usr/share/cmf/schema/scm_prepare_database.sh -h ip-10-0-0-175.eu-west-1.compute.internal mysql scm scm ankara123
    JAVA_HOME=/usr/java/jdk1.8.0_60
    Verifying that we can write to /etc/cloudera-scm-server
    Creating SCM configuration file in /etc/cloudera-scm-server
    Executing:  /usr/java/jdk1.8.0_60/bin/java -cp /usr/share/java/mysql-connector-java.jar:/usr/share/java/oracle-connector-java.jar:/usr/share/cmf/schema/../lib/* com.cloudera.enterprise.dbutil.DbCommandExecutor /etc/cloudera-scm-server/db.properties com.cloudera.cmf.db.
    [                          main] DbCommandExecutor              INFO  Successfully connected to database.
    All done, your SCM database is configured correctly!
  ```
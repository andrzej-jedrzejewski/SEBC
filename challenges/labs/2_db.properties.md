1. First line of the /var/log/cloudera-scm-server/cloudera-scm-server.log (There is one hour shift because I\servers use Ireland time - 8:45 is 9:45 local time)

  ```
    [root@ip-10-0-0-111 yum.repos.d]# head -1 /var/log/cloudera-scm-server/cloudera-scm-server.log
2017-03-10 08:45:52,785 INFO main:com.cloudera.server.cmf.Main: Starting SCM Server. JVM Args: [-Dlog4j.configuration=file:/etc/cloudera-scm-server/log4j.properties, -Dfile.encoding=UTF-8, -Dcmf.root.logger=INFO,LOGFILE, -Dcmf.log.dir=/var/log/cloudera-scm-server, -Dcmf.log.file=cloudera-scm-server.log, -Dcmf.jetty.threshhold=WARN, -Dcmf.schema.dir=/usr/share/cmf/schema, -Djava.awt.headless=true, -Djava.net.preferIPv4Stack=true, -Dpython.home=/usr/share/cmf/python, -XX:+UseConcMarkSweepGC, -XX:+UseParNewGC, -XX:+HeapDumpOnOutOfMemoryError, -Xmx2G, -XX:MaxPermSize=256m, -XX:+HeapDumpOnOutOfMemoryError, -XX:HeapDumpPath=/tmp, -XX:OnOutOfMemoryError=kill -9 %p], Args: [], Version: 5.10.0 (#85 built by jenkins on 20170120-1037 git: aa0b5cd5eceaefe2f971c13ab657020d96bb842a)
  ```

2. Jetty sever line from logs

  ```
    2017-03-10 08:47:13,416 INFO WebServerImpl:com.cloudera.server.cmf.WebServerImpl: Started Jetty server.
  ```

3. db.properties

  ```
    [root@ip-10-0-0-111 yum.repos.d]# cat /etc/cloudera-scm-server/db.properties
    # Auto-generated by scm_prepare_database.sh on Fri Mar 10 08:41:56 UTC 2017
    #
    # For information describing how to configure the Cloudera Manager Server
    # to connect to databases, see the "Cloudera Manager Installation Guide."
    #
    com.cloudera.cmf.db.type=mysql
    com.cloudera.cmf.db.host=ip-10-0-0-175.eu-west-1.compute.internal
    com.cloudera.cmf.db.name=scm
    com.cloudera.cmf.db.user=scm
    com.cloudera.cmf.db.setupType=EXTERNAL
    com.cloudera.cmf.db.password=ankara123
  ```
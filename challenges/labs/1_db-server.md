1. Hostname

  ```
    [root@ip-10-0-0-175 yum.repos.d]# hostname
    ip-10-0-0-175.eu-west-1.compute.internal
  ```

2. The command and output for display your database server's version

  ```
    [root@ip-10-0-0-175 yum.repos.d]# mysql --version
    mysql  Ver 14.14 Distrib 5.6.35, for Linux (x86_64) using  EditLine wrapper
  ```

3. The command and output for listing your created databases

  ```
    [root@ip-10-0-0-175 yum.repos.d]# mysql -u root -p
    Enter password:
    Welcome to the MySQL monitor.  Commands end with ; or \g.
    Your MySQL connection id is 16
    Server version: 5.6.35-log MySQL Community Server (GPL)

    Copyright (c) 2000, 2016, Oracle and/or its affiliates. All rights reserved.

    Oracle is a registered trademark of Oracle Corporation and/or its
    affiliates. Other names may be trademarks of their respective
    owners.

    Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

    mysql> show databases;
    +--------------------+
    | Database           |
    +--------------------+
    | information_schema |
    | hive               |
    | hue                |
    | mysql              |
    | oozie              |
    | performance_schema |
    | rman               |
    | scm                |
    | sentry             |
    +--------------------+
    9 rows in set (0.00 sec)
  ```
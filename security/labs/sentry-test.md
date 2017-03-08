1. Connecto to hive within beeline:

  ```
  beeline -u "jdbc:hive2://ip-10-0-0-206.eu-west-1.compute.internal:10000/default;principal=hive/ip-10-0-0-206.eu-west-1.compute.internal@KAINOS.COM"
  ```

2. Display databases:
  I can see default db but not testdb and tables.

  ```
  jdbc:hive2://ip-10-0-0-206.eu-west-1.compu> show databases;
  INFO  : Compiling command(queryId=hive_20170308154040_bcbc4c4e-d78a-419b-af7c-7e24dc9ed926): show databases
  INFO  : Semantic Analysis Completed
  INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:database_name, type:string, comment:from deserializer)], properties:null)
  INFO  : Completed compiling command(queryId=hive_20170308154040_bcbc4c4e-d78a-419b-af7c-7e24dc9ed926); Time taken: 0.057 seconds
  INFO  : Executing command(queryId=hive_20170308154040_bcbc4c4e-d78a-419b-af7c-7e24dc9ed926): show databases
  INFO  : Starting task [Stage-0:DDL] in serial mode
  INFO  : Completed executing command(queryId=hive_20170308154040_bcbc4c4e-d78a-419b-af7c-7e24dc9ed926); Time taken: 0.118 seconds
  INFO  : OK
  +----------------+--+
  | database_name  |
  +----------------+--+
  | default        |
  +----------------+--+
  1 row selected (0.192 seconds)
  jdbc:hive2://ip-10-0-0-206.eu-west-1.compu> show tables;
    INFO  : Compiling command(queryId=hive_20170308154949_22bd6852-23ce-4698-a19f-7020d15dc055): show tables
    INFO  : Semantic Analysis Completed
    INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
    INFO  : Completed compiling command(queryId=hive_20170308154949_22bd6852-23ce-4698-a19f-7020d15dc055); Time taken: 0.057 seconds
    INFO  : Executing command(queryId=hive_20170308154949_22bd6852-23ce-4698-a19f-7020d15dc055): show tables
    INFO  : Starting task [Stage-0:DDL] in serial mode
    INFO  : Completed executing command(queryId=hive_20170308154949_22bd6852-23ce-4698-a19f-7020d15dc055); Time taken: 0.114 seconds
    INFO  : OK
    +-----------+--+
    | tab_name  |
    +-----------+--+
    +-----------+--+
    1 row selected (0.187 seconds)
  ```

3. Show roles:
   There is no roles.

  ```
    0: jdbc:hive2://ip-10-0-0-206.eu-west-1.compu> show roles;
    INFO  : Compiling command(queryId=hive_20170308154141_12867dda-94e7-4d4e-97a7-ac07004bf925): show roles
    INFO  : Semantic Analysis Completed
    INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:role, type:string, comment:from deserializer)], properties:null)
    INFO  : Completed compiling command(queryId=hive_20170308154141_12867dda-94e7-4d4e-97a7-ac07004bf925); Time taken: 0.088 seconds
    INFO  : Executing command(queryId=hive_20170308154141_12867dda-94e7-4d4e-97a7-ac07004bf925): show roles
    INFO  : Starting task [Stage-0:DDL] in serial mode
    INFO  : Completed executing command(queryId=hive_20170308154141_12867dda-94e7-4d4e-97a7-ac07004bf925); Time taken: 0.024 seconds
    INFO  : OK
    +-------+--+
    | role  |
    +-------+--+
    +-------+--+
    No rows selected (0.123 seconds)
  ```

4. Let's create a role and assign it to my group. I can see all dbs and tables;

  ```
    INFO  : Compiling command(queryId=hive_20170308154848_f18bdeb4-4d1e-4a16-a167-6d64beddd85c): show databases
    INFO  : Semantic Analysis Completed
    INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:database_name, type:string, comment:from deserializer)], properties:null)
    INFO  : Completed compiling command(queryId=hive_20170308154848_f18bdeb4-4d1e-4a16-a167-6d64beddd85c); Time taken: 0.068 seconds
    INFO  : Executing command(queryId=hive_20170308154848_f18bdeb4-4d1e-4a16-a167-6d64beddd85c): show databases
    INFO  : Starting task [Stage-0:DDL] in serial mode
    INFO  : Completed executing command(queryId=hive_20170308154848_f18bdeb4-4d1e-4a16-a167-6d64beddd85c); Time taken: 0.146 seconds
    INFO  : OK
    +----------------+--+
    | database_name  |
    +----------------+--+
    | default        |
    | testdb         |
    +----------------+--+
    2 rows selected (0.228 seconds)
    0: jdbc:hive2://ip-10-0-0-206.eu-west-1.compu> show tables;
    INFO  : Compiling command(queryId=hive_20170308154949_22bd6852-23ce-4698-a19f-7020d15dc055): show tables
    INFO  : Semantic Analysis Completed
    INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
    INFO  : Completed compiling command(queryId=hive_20170308154949_22bd6852-23ce-4698-a19f-7020d15dc055); Time taken: 0.057 seconds
    INFO  : Executing command(queryId=hive_20170308154949_22bd6852-23ce-4698-a19f-7020d15dc055): show tables
    INFO  : Starting task [Stage-0:DDL] in serial mode
    INFO  : Completed executing command(queryId=hive_20170308154949_22bd6852-23ce-4698-a19f-7020d15dc055); Time taken: 0.114 seconds
    INFO  : OK
    +-----------+--+
    | tab_name  |
    +-----------+--+
    | employee  |
    +-----------+--+
    1 row selected (0.187 seconds)
  ```

5. Let's test goerge user:

  ```
  [andrzej-jedrzejewski@ip-10-0-0-206 ~]$ kinit goerge
  kinit: Client 'goerge@KAINOS.COM' not found in Kerberos database while getting initial credentials
  [andrzej-jedrzejewski@ip-10-0-0-206 ~]$ kinit george
  Password for george@KAINOS.COM:
  [andrzej-jedrzejewski@ip-10-0-0-206 ~]$ beeline -u "jdbc:hive2://ip-10-0-0-206.eu-west-1.compute.internal:10000/default;principal=hive/ip-10-0-0-206.eu-west-1.compute.internal@KAINOS.COM"
  Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
  Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
  scan complete in 2ms
  Connecting to jdbc:hive2://ip-10-0-0-206.eu-west-1.compute.internal:10000/default;principal=hive/ip-10-0-0-206.eu-west-1.compute.internal@KAINOS.COM
  Connected to: Apache Hive (version 1.1.0-cdh5.8.4)
  Driver: Hive JDBC (version 1.1.0-cdh5.8.4)
  Transaction isolation: TRANSACTION_REPEATABLE_READ
  Beeline version 1.1.0-cdh5.8.4 by Apache Hive
  0: jdbc:hive2://ip-10-0-0-206.eu-west-1.compu> show tables;
  INFO  : Compiling command(queryId=hive_20170308155454_8d191ec7-3e91-43b4-893e-54c823cbf541): show tables
  INFO  : Semantic Analysis Completed
  INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
  INFO  : Completed compiling command(queryId=hive_20170308155454_8d191ec7-3e91-43b4-893e-54c823cbf541); Time taken: 0.069 seconds
  INFO  : Executing command(queryId=hive_20170308155454_8d191ec7-3e91-43b4-893e-54c823cbf541): show tables
  INFO  : Starting task [Stage-0:DDL] in serial mode
  INFO  : Completed executing command(queryId=hive_20170308155454_8d191ec7-3e91-43b4-893e-54c823cbf541); Time taken: 0.108 seconds
  INFO  : OK
  +-----------+--+
  | tab_name  |
  +-----------+--+
  | employee  |
  +-----------+--+
  1 row selected (0.28 seconds)
  0: jdbc:hive2://ip-10-0-0-206.eu-west-1.compu>
  ```


6. Let's test ferdinand user:

  ```
  [andrzej-jedrzejewski@ip-10-0-0-206 ~]$ kinit ferdinand
  Password for ferdinand@KAINOS.COM:
  [andrzej-jedrzejewski@ip-10-0-0-206 ~]$ beeline -u "jdbc:hive2://ip-10-0-0-206.eu-west-1.compute.internal:10000/default;principal=hive/ip-10-0-0-206.eu-west-1.compute.internal@KAINOS.COM"
  Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
  Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
  scan complete in 2ms
  Connecting to jdbc:hive2://ip-10-0-0-206.eu-west-1.compute.internal:10000/default;principal=hive/ip-10-0-0-206.eu-west-1.compute.internal@KAINOS.COM
  Connected to: Apache Hive (version 1.1.0-cdh5.8.4)
  Driver: Hive JDBC (version 1.1.0-cdh5.8.4)
  Transaction isolation: TRANSACTION_REPEATABLE_READ
  Beeline version 1.1.0-cdh5.8.4 by Apache Hive
  0: jdbc:hive2://ip-10-0-0-206.eu-west-1.compu> show tables;
  INFO  : Compiling command(queryId=hive_20170308155555_ca1c466c-ef5c-4f23-bf32-299d231d6daa): show tables
  INFO  : Semantic Analysis Completed
  INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
  INFO  : Completed compiling command(queryId=hive_20170308155555_ca1c466c-ef5c-4f23-bf32-299d231d6daa); Time taken: 0.056 seconds
  INFO  : Executing command(queryId=hive_20170308155555_ca1c466c-ef5c-4f23-bf32-299d231d6daa): show tables
  INFO  : Starting task [Stage-0:DDL] in serial mode
  INFO  : Completed executing command(queryId=hive_20170308155555_ca1c466c-ef5c-4f23-bf32-299d231d6daa); Time taken: 0.111 seconds
  INFO  : OK
  +-----------+--+
  | tab_name  |
  +-----------+--+
  +-----------+--+
  No rows selected (0.265 seconds)
  ```



1. What is ubertask optimization?
   Within an uber optimization we can run MR tasks AM JVM if the job is small enough.

    ```
       Whether to enable ubertask optimization, which runs "sufficiently small" jobs sequentially within a single JVM. "Small" is defined by the mapreduce.job.ubertask.maxmaps, mapreduce.job.ubertask.maxreduces, and mapreduce.job.ubertask.maxbytes settings.
    ```

2. Where in CM is the Kerberos Security Realm value displayed?

   ```
      default_realm
   ```

3. Which CDH service(s) host a property for enabling Kerberos authentication?

    ```
      All services can use Kerberos authentication
    ```

4. How do you upgrade the CM agents?

    ```
      We can use Upgrade Wizard or do it manually
    ```

5. Give the tsquery statement used to chart Hue's CPU utilization?

    ```
      Hue CPU core used or select cgroup_cpu_system_rate, cpu_user_rate where serviceType = HUE
    ```

6. Name all the roles that make up the Hive service

    ```
      - HiveServer2
      - Hive Metastore
      - Hive Gateway
    ```

7. What steps must be completed before integrating Cloudera Manager with Kerberos?

    ```
      - Decide about KDC type (MIT or AD)
      - Install required packages for your OS (openldap-clients on the Cloudera Manager Server host
        krb5-workstation, krb5-libs on ALL hosts)
      - If You are Using AES-256 Encryption, Install the JCE Policy File
      - Get or Create a Kerberos Principal for the Cloudera Manager Server
      - Enabling Kerberos Using the Wizard
      - Create the HDFS Superuser
      - Get or Create a Kerberos Principal for Each User Account
      - Prepare the Cluster for Each User
      - Verify that Kerberos Security is Working
      - (Optional) Enable Authentication for HTTP Web Consoles for Hadoop Roles
    ```

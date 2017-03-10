1. Mysql repos:

  ```
    [root@ip-10-0-0-175 yum.repos.d]# cat /etc/yum.repos.d/mysql-community.repo
    [mysql56-community]
    name=MySQL 5.6 Community Server
    baseurl=http://repo.mysql.com/yum/mysql-5.6-community/el/7/$basearch/
    enabled=1
    gpgcheck=0
    gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-mysql
  ```
2. Change in my.cnf with cloudera recommendations:

  ```
    [mysqld]
    transaction-isolation = READ-COMMITTED
    # Disabling symbolic-links is recommended to prevent assorted security risks;
    # to do so, uncomment this line:
    # symbolic-links = 0

    key_buffer = 16M
    key_buffer_size = 32M
    max_allowed_packet = 32M
    thread_stack = 256K
    thread_cache_size = 64
    query_cache_limit = 8M
    query_cache_size = 64M
    query_cache_type = 1

    max_connections = 550
    #expire_logs_days = 10
    #max_binlog_size = 100M

    #log_bin should be on a disk with enough free space. Replace '/var/lib/mysql/mysql_binary_log' with an appropriate path for your system
    #and chown the specified folder to the mysql user.
    log_bin=/var/lib/mysql/mysql_binary_log

    binlog_format = mixed

    read_buffer_size = 2M
    read_rnd_buffer_size = 16M
    sort_buffer_size = 8M
    join_buffer_size = 8M

    # InnoDB settings
    innodb_file_per_table = 1
    innodb_flush_log_at_trx_commit  = 2
    innodb_log_buffer_size = 64M
    innodb_buffer_pool_size = 4G
    innodb_thread_concurrency = 8
    innodb_flush_method = O_DIRECT
    innodb_log_file_size = 512M

    [mysqld_safe]
    log-error=/var/log/mysqld.log
    pid-file=/var/run/mysqld/mysqld.pid
  ```

3. Start mysqld service:

  ```
    [root@ip-10-0-0-175 yum.repos.d]# systemctl status mysqld
    ● mysqld.service - MySQL Community Server
       Loaded: loaded (/usr/lib/systemd/system/mysqld.service; enabled; vendor preset: disabled)
       Active: active (running) since Fri 2017-03-10 08:23:32 UTC; 5s ago
      Process: 9347 ExecStartPost=/usr/bin/mysql-systemd-start post (code=exited, status=0/SUCCESS)
      Process: 9283 ExecStartPre=/usr/bin/mysql-systemd-start pre (code=exited, status=0/SUCCESS)
     Main PID: 9346 (mysqld_safe)
       CGroup: /system.slice/mysqld.service
               ├─9346 /bin/sh /usr/bin/mysqld_safe --basedir=/usr
               └─9740 /usr/sbin/mysqld --basedir=/usr --datadir=/var/lib/mysql --plugin-dir=/usr/lib64/mysql/plugin --log-error=/var/log/mysqld.log --pid-file=/var/run/mysqld/mysqld.pid
  ```


















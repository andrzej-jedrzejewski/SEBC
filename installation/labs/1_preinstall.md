1. To change swappiness option we can use:

  ```
  sysctl vm.swappiness=1
  echo "vm.swappiness = 1" >> /etc/sysctl.conf
  ```
  To verify on each host:
  ```
  [root@ip-10-0-0-206 ec2-user]# cat /etc/sysctl.d/swappiness.conf
  vm.swappiness=1
  ```

2. mount attribute output:
  ```
  [root@ip-10-0-0-206 ec2-user]# mount
  sysfs on /sys type sysfs (rw,nosuid,nodev,noexec,relatime,seclabel)
  proc on /proc type proc (rw,nosuid,nodev,noexec,relatime)
  devtmpfs on /dev type devtmpfs (rw,nosuid,seclabel,size=7599360k,nr_inodes=1899840,mode=755)
  securityfs on /sys/kernel/security type securityfs (rw,nosuid,nodev,noexec,relatime)
  tmpfs on /dev/shm type tmpfs (rw,nosuid,nodev,seclabel)
  devpts on /dev/pts type devpts (rw,nosuid,noexec,relatime,seclabel,gid=5,mode=620,ptmxmode=000)
  tmpfs on /run type tmpfs (rw,nosuid,nodev,seclabel,mode=755)
  tmpfs on /sys/fs/cgroup type tmpfs (ro,nosuid,nodev,noexec,seclabel,mode=755)
  cgroup on /sys/fs/cgroup/systemd type cgroup (rw,nosuid,nodev,noexec,relatime,xattr,release_agent=/usr/lib/systemd/systemd-cgroups-agent,name=systemd)
  pstore on /sys/fs/pstore type pstore (rw,nosuid,nodev,noexec,relatime)
  cgroup on /sys/fs/cgroup/devices type cgroup (rw,nosuid,nodev,noexec,relatime,devices)
  cgroup on /sys/fs/cgroup/hugetlb type cgroup (rw,nosuid,nodev,noexec,relatime,hugetlb)
  cgroup on /sys/fs/cgroup/perf_event type cgroup (rw,nosuid,nodev,noexec,relatime,perf_event)
  cgroup on /sys/fs/cgroup/freezer type cgroup (rw,nosuid,nodev,noexec,relatime,freezer)
  cgroup on /sys/fs/cgroup/memory type cgroup (rw,nosuid,nodev,noexec,relatime,memory)
  cgroup on /sys/fs/cgroup/cpu,cpuacct type cgroup (rw,nosuid,nodev,noexec,relatime,cpuacct,cpu)
  cgroup on /sys/fs/cgroup/blkio type cgroup (rw,nosuid,nodev,noexec,relatime,blkio)
  cgroup on /sys/fs/cgroup/net_cls type cgroup (rw,nosuid,nodev,noexec,relatime,net_cls)
  cgroup on /sys/fs/cgroup/cpuset type cgroup (rw,nosuid,nodev,noexec,relatime,cpuset)
  configfs on /sys/kernel/config type configfs (rw,relatime)
  /dev/xvda2 on / type xfs (rw,relatime,seclabel,attr2,inode64,noquota)
  selinuxfs on /sys/fs/selinux type selinuxfs (rw,relatime)
  systemd-1 on /proc/sys/fs/binfmt_misc type autofs (rw,relatime,fd=31,pgrp=1,timeout=300,minproto=5,maxproto=5,direct)
  debugfs on /sys/kernel/debug type debugfs (rw,relatime)
  hugetlbfs on /dev/hugepages type hugetlbfs (rw,relatime,seclabel)
  mqueue on /dev/mqueue type mqueue (rw,relatime,seclabel)
  binfmt_misc on /proc/sys/fs/binfmt_misc type binfmt_misc (rw,relatime)
  tmpfs on /run/user/0 type tmpfs (rw,nosuid,nodev,relatime,seclabel,size=1497312k,mode=700)
  tmpfs on /run/user/995 type tmpfs (rw,nosuid,nodev,relatime,seclabel,size=1497312k,mode=700,uid=995,gid=992)
  tmpfs on /run/user/1000 type tmpfs (rw,nosuid,nodev,relatime,seclabel,size=1497312k,mode=700,uid=1000,gid=1000)
  cm_processes on /run/cloudera-scm-agent/process type tmpfs (rw,relatime,seclabel,mode=751)
  ```

3. Show the reserve space of any non-root, ext-based volumes: 
  ```
    There is only one physical/logical volume (root) - Saving my $$$ :)
  ```
4. Disabling Transparent Hugepage Compaction

  ```
    if [ -f /sys/kernel/mm/redhat_transparent_hugepage/defrag ];
  then
    echo "never" > /sys/kernel/mm/redhat_transparent_hugepage/defrag
    echo 'echo "never" > /sys/kernel/mm/redhat_transparent_hugepage/defrag' >> /etc/rc.local
  else
    echo "never" > /sys/kernel/mm/transparent_hugepage/defrag
    echo 'echo "never" > /sys/kernel/mm/transparent_hugepage/defrag' >> /etc/rc.local
  fi
  if [ -f /sys/kernel/mm/redhat_transparent_hugepage/enabled ];
  then
    echo "never" > /sys/kernel/mm/redhat_transparent_hugepage/enabled
    echo 'echo "never" > /sys/kernel/mm/redhat_transparent_hugepage/enabled' >> /etc/rc.local
  else
    echo "never" > /sys/kernel/mm/transparent_hugepage/enabled
    echo 'echo "never" > /sys/kernel/mm/transparent_hugepage/enabled' >> /etc/rc.local
  fi
  ```
  To verify on each host:
  ```
  [root@ip-10-0-0-206 ec2-user]# cat /sys/kernel/mm/transparent_hugepage/defrag
  always madvise [never]
  ```
5. List your network interface configuration
    ```
    [root@ip-10-0-0-206 ec2-user]# ifconfig
        eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9001
        inet 10.0.0.206  netmask 255.255.255.0  broadcast 10.0.0.255
        inet6 fe80::8b:9ff:fe53:32cd  prefixlen 64  scopeid 0x20<link>
        ether 02:8b:09:53:32:cd  txqueuelen 1000  (Ethernet)
        RX packets 2907687  bytes 3176397396 (2.9 GiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 2848257  bytes 3562950523 (3.3 GiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

        lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 0  (Local Loopback)
        RX packets 2600057  bytes 4659527583 (4.3 GiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 2600057  bytes 4659527583 (4.3 GiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
    ``

6. a) Forward DNS lookup
      ```
      root@ip-10-0-0-206 ec2-user]# nslookup ip-10-0-0-206.eu-west-1.compute.internal
      Server:   10.0.0.2
      Address:  10.0.0.2#53

      Non-authoritative answer:
      Name: ip-10-0-0-206.eu-west-1.compute.internal
      Address: 10.0.0.206
      ```
    b) Reverse DNS lookup
      ```
      root@ip-10-0-0-206 ec2-user]# nslookup 10.0.0.206
      Server:   10.0.0.2
      Address:  10.0.0.2#53
      Non-authoritative answer:
      206.0.0.10.in-addr.arpa name = ip-10-0-0-206.eu-west-1.compute.internal.
      ```
7. Status of nscd:
   ```
   [root@ip-10-0-0-206 ec2-user]# systemctl status nscd
    ● nscd.service - Name Service Cache Daemon
    Loaded: loaded (/usr/lib/systemd/system/nscd.service; enabled; vendor preset: disabled)
    **Active: active (running)** since Mon 2017-03-06 19:34:33 UTC; 2h 39min ago
    Main PID: 18350 (nscd)
    CGroup: /system.slice/nscd.service
           └─18350 /usr/sbin/nscd
    ```
    
8. Status of ntp:
    ```
   [root@ip-10-0-0-206 ec2-user]# systemctl status ntpd
    ● ntpd.service - Network Time Service
    Loaded: loaded (/usr/lib/systemd/system/ntpd.service; enabled; vendor preset: disabled)
    **Active: active (running)** since Mon 2017-03-06 19:34:33 UTC; 2h 40min ago
    Main PID: 18306 (ntpd)
    CGroup: /system.slice/ntpd.service
           └─18306 /usr/sbin/ntpd -u ntp:ntp -g
   ```

9. Host inspector screenshot:
   ![AWS Nodes](https://github.com/andrzej-jedrzejewski/SEBC/blob/master/installation/png/host_inspector.png)


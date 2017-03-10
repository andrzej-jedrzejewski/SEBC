1. Cloud provider

  ```
    AWS
  ```
2. IPs
  
  ```
    34.251.147.51 10.0.0.175 ip-10-0-0-175.eu-west-1.compute.internal
    34.252.80.213 10.0.0.111 ip-10-0-0-111.eu-west-1.compute.internal
    34.251.185.37 10.0.0.194 ip-10-0-0-194.eu-west-1.compute.internal
    34.252.82.242 10.0.0.77  ip-10-0-0-77.eu-west-1.compute.internal
    34.251.39.66  10.0.0.96  ip-10-0-0-96.eu-west-1.compute.internal
  ```

3. OS release 
  ```
    [root@ip-10-0-0-175 ec2-user]# cat /etc/redhat-release
    Red Hat Enterprise Linux Server release 7.3 (Maipo)
  ```

4. Disk
  ```
    [root@ip-10-0-0-175 ec2-user]# df -hT
    Filesystem     Type      Size  Used Avail Use% Mounted on
    /dev/xvda2     xfs        50G  2.2G   48G   5% /
    devtmpfs       devtmpfs  7.3G     0  7.3G   0% /dev
    tmpfs          tmpfs     7.2G     0  7.2G   0% /dev/shm
    tmpfs          tmpfs     7.2G   25M  7.2G   1% /run
    tmpfs          tmpfs     7.2G     0  7.2G   0% /sys/fs/cgroup
    tmpfs          tmpfs     1.5G     0  1.5G   0% /run/user/1000
    tmpfs          tmpfs     1.5G     0  1.5G   0% /run/user/0
  ```

5. Repolist:
  ```
    [root@ip-10-0-0-175 ec2-user]# yum repolist enabled
    Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
    repo id                                          repo name                                       status
    rhui-REGION-client-config-server-7/x86_64        Red Hat Update Infrastructure 2.0 Client Config      6
    rhui-REGION-rhel-server-releases/7Server/x86_64  Red Hat Enterprise Linux Server 7 (RPMs)        14,038
    rhui-REGION-rhel-server-rh-common/7Server/x86_64 Red Hat Enterprise Linux Server 7 RH Common (RP    209
    repolist: 14,253
  ```

6. Output of /etc/passwd:

  ```
    [root@ip-10-0-0-175 ec2-user]# cat /etc/passwd | grep 'neymar\|ronaldo'
    neymar:x:2010:2010::/home/neymar:/bin/bash
    ronaldo:x:2016:2016::/home/ronaldo:/bin/bash
  ```
7. Output of /etc/groups"

  ```
    [root@ip-10-0-0-175 ec2-user]# cat /etc/group | grep 'merengues\|barca'
    barca:x:2017:ronaldo
    merengues:x:2018:neymar
  ```













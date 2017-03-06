To change swappiness option we can use:

```
sysctl vm.swappiness=1
echo "vm.swappiness = 1" >> /etc/sysctl.conf
```
To verify on each host:
```
[root@ip-10-0-0-206 ec2-user]# cat /etc/sysctl.d/swappiness.conf
vm.swappiness=1
```

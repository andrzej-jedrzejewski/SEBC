1. Authenticate with keytab:

  ```
  [andrzej-jedrzejewski@ip-10-0-0-206 ~]$ kdestroy
  [andrzej-jedrzejewski@ip-10-0-0-206 ~]$ klist
  klist: No credentials cache found (filename: /tmp/krb5cc_1002)

  [andrzej-jedrzejewski@ip-10-0-0-206 ~]$ kinit -k -t andrzej.keytab andrzej-jedrzejewski@KAINOS.COM
  [andrzej-jedrzejewski@ip-10-0-0-206 ~]$ klist
  Ticket cache: FILE:/tmp/krb5cc_1002
  Default principal: andrzej-jedrzejewski@KAINOS.COM

  Valid starting       Expires              Service principal
  03/08/2017 14:16:09  03/09/2017 14:16:09  krbtgt/KAINOS.COM@KAINOS.COM
    renew until 03/15/2017 14:16:09
  ```

2. Authenticate with kinit:

  ```
  [andrzej-jedrzejewski@ip-10-0-0-206 ~]$ kdestroy
  [andrzej-jedrzejewski@ip-10-0-0-206 ~]$ kinit
  Password for andrzej-jedrzejewski@KAINOS.COM:
  [andrzej-jedrzejewski@ip-10-0-0-206 ~]$ klist
  Ticket cache: FILE:/tmp/krb5cc_1002
  Default principal: andrzej-jedrzejewski@KAINOS.COM

  Valid starting       Expires              Service principal
  03/08/2017 14:26:21  03/09/2017 14:26:21  krbtgt/KAINOS.COM@KAINOS.COM
    renew until 03/15/2017 14:26:21
  ```
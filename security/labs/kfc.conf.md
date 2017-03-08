```
# Configuration snippets may be placed in this directory as well
includedir /etc/krb5.conf.d/

[logging]
 default = FILE:/var/log/krb5libs.log
 kdc = FILE:/var/log/krb5kdc.log
 admin_server = FILE:/var/log/kadmind.log

[libdefaults]
 default_realm = KAINOS.COM
 dns_lookup_kdc = false
 dns_lookup_realm = false
 ticket_lifetime = 86400
 renew_lifetime = 604800
 forwardable = true
 default_tgs_enctypes = arcfour-hmac
 default_tkt_enctypes = arcfour-hmac
 permitted_enctypes = arcfour-hmac
 udp_preference_limit = 1
 kdc_timeout = 3000

[realms]
KAINOS.COM = {
  kdc = ip-10-0-0-206.eu-west-1.compute.internal
  admin_server = ip-10-0-0-206.eu-west-1.compute.internal
 }

[domain_realm]
 .example.com = KAINOS.COM
 example.com = KAINOS.COM
```
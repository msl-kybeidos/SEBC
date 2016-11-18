```
[logging]
 default = FILE:/var/log/krb5libs.log
 kdc = FILE:/var/log/krb5kdc.log
 admin_server = FILE:/var/log/kadmind.log

[libdefaults]
 default_realm = MSL-KYBEIDOS.DE
 dns_lookup_realm = false
 dns_lookup_kdc = false
 ticket_lifetime = 24h
 renew_lifetime = 7d
 forwardable = true
 udp_preference_limit = 1
 default_tgs_enctypes = arcfour-hmac
 default_tkt_enctypes = arcfour-hmac

[realms]
 MSL-KYBEIDOS.DE = {
  kdc = ip-172-31-9-122.ec2.internal
  admin_server = ip-172-31-9-122.ec2.internal
 }

[domain_realm]
 .example.com = MSL-KYBEIDOS.DE
 example.com = MSL-KYBEIDOS.DE
```
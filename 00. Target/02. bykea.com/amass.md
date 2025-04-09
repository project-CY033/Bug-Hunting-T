## **amass**    

```
amass enum -passive -d bykea.com -o amass.txt -v
```

### output 
```

bykea.com (FQDN) --> ns_record --> sharon.ns.cloudflare.com (FQDN)                                                     
bykea.com (FQDN) --> ns_record --> stan.ns.cloudflare.com (FQDN)
bykea.com (FQDN) --> mx_record --> alt2.aspmx.l.google.com (FQDN)
bykea.com (FQDN) --> mx_record --> alt3.aspmx.l.google.com (FQDN)
example.com (FQDN) --> ns_record --> a.iana-servers.net (FQDN)
example.com (FQDN) --> ns_record --> b.iana-servers.net (FQDN)
bykea.com (FQDN) --> mx_record --> aspmx.l.google.com (FQDN)
bykea.com (FQDN) --> mx_record --> alt4.aspmx.l.google.com (FQDN)
bykea.com (FQDN) --> mx_record --> alt1.aspmx.l.google.com (FQDN)
www.example.com (FQDN) --> cname_record --> www.example.com-v4.edgesuite.net (FQDN)
stan.ns.cloudflare.com (FQDN) --> a_record --> 172.64.33.235 (IPAddress)
stan.ns.cloudflare.com (FQDN) --> a_record --> 108.162.193.235 (IPAddress)
stan.ns.cloudflare.com (FQDN) --> a_record --> 173.245.59.235 (IPAddress)
stan.ns.cloudflare.com (FQDN) --> aaaa_record --> 2803:f800:50::6ca2:c1eb (IPAddress)
stan.ns.cloudflare.com (FQDN) --> aaaa_record --> 2a06:98c1:50::ac40:21eb (IPAddress)
stan.ns.cloudflare.com (FQDN) --> aaaa_record --> 2606:4700:58::adf5:3beb (IPAddress)
173.245.58.0/23 (Netblock) --> contains --> 173.245.59.235 (IPAddress)
172.64.0.0/18 (Netblock) --> contains --> 172.64.33.235 (IPAddress)
108.162.192.0/20 (Netblock) --> contains --> 108.162.193.235 (IPAddress)
13335 (ASN) --> managed_by --> CLOUDFLARENET - Cloudflare, Inc. (RIROrganization)
13335 (ASN) --> announces --> 173.245.58.0/23 (Netblock)
13335 (ASN) --> announces --> 172.64.0.0/18 (Netblock)
13335 (ASN) --> announces --> 108.162.192.0/20 (Netblock)
2a06:98c1:50::/46 (Netblock) --> contains --> 2a06:98c1:50::ac40:21eb (IPAddress)
2803:f800:50::/45 (Netblock) --> contains --> 2803:f800:50::6ca2:c1eb (IPAddress)
13335 (ASN) --> announces --> 2a06:98c1:50::/46 (Netblock)
13335 (ASN) --> announces --> 2803:f800:50::/45 (Netblock)
2606:4700:58::/48 (Netblock) --> contains --> 2606:4700:58::adf5:3beb (IPAddress)
0 (ASN) --> managed_by --> Unknown (RIROrganization)
0 (ASN) --> announces --> 2606:4700:58::/48 (Netblock)




```

---
---

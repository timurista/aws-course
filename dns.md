# DNS 101
TTL and a record
DNS is domain, phone book jsmith you do dns search from acloud.guru to idnetify the ip address.
IP 4 been around as long as internet, 32bit field. Scaling was the problem, new device onto internet it needed a new address.
IP 6 was created to solve depletion issue, 340 ndecillion addresses. ISP should be making end uses to ip6. IP 6, VPC and couldn't do it with ec2 instances, but as of 2016 VPC are IPv6 compatible

## Domain names
last word is top level
top level domain name => .com, .edu
second level is edu, com
http://www.iana.org/domains/root/db

## Domain registrars
assigns InterNIC, ICANN, whois domain db.

SOA Records, name of the server supplied data for the zone, admin of the zone

## NS Records
zone in root 53, ns records you go to go dady console supply domain registrar. Amazon is domain registrar. Use aws as domain registrar.

## A Records
Must fundamental type, A. acould.ugur => 123.10.10.80. Domain name acloud.guru.com. It resolves to elastic load baalncer, always have DNS name. You can't use a record 

## TTL
lenght of time it is cached Time to live, pc checks to see if it has that address in cache, you go to root 53. Then you get ip4 address it will be cached locally, if you do dns migration. Before they do it, they drop ttl to 5 minutes then wait 2 days before do migration. If you don't do it dns requests will go to old site.

## CNAME
resolve myname.com, you can have it to some other place.
m.acloud.guru...  also mobile.acloud.guru. You can have 


## ALias record (amazon)
s3 buckets, like cname you can map one name to another/ ELB, naked domain name. Key difference, automatically maps zone apex domain name to ELB.

can save time, recognize changes in record set. example.com => elb, lb1--....com, if IP address of ELB changes, Route 53 will update.

## Exam tips
ELB no predefined IPv4, dns enpoint point. Naked domain name you need... alias records you can resolve naked domain name to address. Charged for request if using cnames, you won't be charged if Alias. 9/10 Alias record, not charged you can make naked domain name.


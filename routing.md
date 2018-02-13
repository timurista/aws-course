## Routing Policies

Simple is the defalt routing policy when you create a new record

user makes dns request -> route 53 -> to ec2 in particular region

services -> route 53
  Hosted Zone
  2 record sets

top level domains
  co, link dns record to ec2 instances
  record set
  alias for zone apex --> naked domain name

alias target
  london and sydney

type is  A record, just an alias
  hellocloudgurus.com -> elb

## Weighted Routing Policies
User -> hellocloud gurus -> route 53 can send 20% to us east 1, 80% to us west 1
- a and b testing website, new ux trying to increase sales
- 2 elb in same region, 80% behind one load baalncer
- split traffic based on weights assigned

my sydney site
### Routing Policy
  weight of 30
  same name

A and B, want to sent traffic to new website until you take it out of development and into testing

Routing policies

### Latency Routing Policy
which region will give them the fastest response time
route 53 will give them

user south africa --> hellocloudgurus -> route 53 (54ms to go to london) --> but sydney site takes 300ms
so route 53 would send it to eu west2, will feel faster

## Failover
route 53 will monitor health of primary site, and if it fails will send to sydney

active --> London (active site)
passive --> Sydeny
if London fails, route 53 will send all traffic to Sydney

Health check
  ed2 ELB --> primary 
  configure health check (my london health check)

## geolocation
route traffic depending on geographical location of user. Europe --> servers like local languages and all prices are in euros. etc

create record set
zone apex. you select routing policy of geolocation

## Summary
ELB cost money, please delete them
can never have an ip 4 of elb, never buplic. YOu resolve to them using DNS name

Alias record -> can resolve individual aws resources like elb, 
use alias record over cname
CNAME (similar to alias, uses public dns)

Routing Policies
  Simple, round robin
  Weighted, A-B testing
  Latency, ende user quickest performance
  Failover, prod and dr site
  Geolocation, end users are (send us to us website and european to european)

Route 53 supports MX Records
Route53 is named so because The DNS Port is on Port 53 and Route53 is DNS service
Route53 does sipport zone apex records or naked domain names

There is a limit to number of domain names you can manager using route 53
Incorrect. There is 50 domain names available by default, however it is a soft limit and can be raised by contacting AWS support. http://aws.amazon.com/route53/faqs/
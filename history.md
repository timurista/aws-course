# History AWS

## Where has it come from?
1) invetion, try alot of experiments
2) not dammage of collateral dammage of failed experiments

install, load balancers, awful lot of time
  literally provision complex env really quickly using scripted infrastructure

2003 ~ black and pinkhan, aws internal structure
  sell it as a service
  sqs 2004 first aws service
    1-2 services, console was easy to use
  
2010 all of amazon.com moved over to it
  2012 reinvent conference, 44 people

2014 AWS certifications,
  2016 run rate 13 bill, AI services and VR services

Gartner's Magic Quadrant
  AWS dominating for a very long time
  leader for 6th year, microsoft then by google
    get AWS certified, possibly azure


## AWS global infrastructure

compute, storage, databases
migrations, machine learning... etc

aws global infrastructure
  16 regions, 44 availability zones

you need to understand concepts

# Regions
  geographical area
  2 or more availability zone
    **data center**
    in a region, but far enough apart won't affect
    
Note spread resources across multiple availability zones

## Availability ZOne
  Data Center, far enough apart wont get affected by outage at one location

## AWS Edge Locations
  endpoints for aws for caching content

## Regions
  consistent of 2 or more discrete Availability zones

CDN, they need to pull stuff down
  edge location will cache info

cache pictures, or videos at a location close to them
  any other person trying to access it will just pull it down

96 edge locations

EXam tips
KNOW difference Region (2 or more av zones), Availability 1 or more discrete data centers with redundant power connectivity, far enough apart issue with one will not affect, CloudFront / Availability endpoints


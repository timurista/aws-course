## Aws services

platform
1) global infrastructure
- different regions,
- regions has "availability zone" at least 2 per region, data centers (geographically isolated)
- edge locations (cache data), cloud front (cdn)

tons of services
  network,
  developer tools,
  storage,
  iot,
  game development,
  etc...

wholistic view
  know what a service is

1) Compute
  EC2 - ELASTIC COMPUTE CLOUD, vm inside aws platform
  EC2 COntainer Service - docker container at scale
  Elastic Beanstalk - autoscaling groups, load balancers, etc., devops pro course
  Lambda - code -> cloud you control when it executes (nothing to manage). MEAN website, you create lambda to put text over top. Triggered, senses image uploaded it writes text and outputs it.

  Lightsail
    amazon virtual private server, provision with server. Fixed ip you login RDP access or SSH access linux. Watered down version of ec2

  Batch
    batch computing, if you want to do batch computing in cloud

2) Storage
  s3 -- simple storage service. Object based storage. You have buckets and you upload to cloud
  efs -- network attached storage
  glacier -- check it every year or so but to store for very cheap
  snowball -- lots of data into data center (availability zone)
  storage gateway -vm you install in head office, replicate information back to S3

3) Databases
  RDS, mysql, postgres sql, aurora, oracle
  DynamoDB
  Elasticache -- cache common queried things from DB server (top 10 products)
  Red Shift -- built for data wharehousing

4) Migration
  AWS Migration Hub -- trck app as you migrate them to AWS
  Application Discovery Service -- detects dependencies, like share server
  Database Migration Service -- 
  Server Migration Service -- migrate them 
  Snowball -- storage and migration (large data into cloud)

5) Network Content
  VPC -- virtual data center, firewwalls, availability zones, root tables, etc., IMPORTANT, understand. Build it by memory, pretty easy
  CloudFront -- Amazon content delivery network. media, video files, images, etc. Store it closer to users in Australia.
    get from edge location
  Route53 -- DNS service, lookup jsmith you get name and telephone for him. IPV4 and IPV6 address
  API Gateway -- when we create serverless website with poly. Create own apis with other services to talk to
  Direct Connect -- running dedicated line from corporate office to location

6) Developer Tools
  nothing but have an idea
  CodeStar -- get a group of devs working together, project managing code. Continous delivery tool chain.
  CodeCommit -- store code, source control, store private git
  CodeBuild -- compiles code, run tests and produce packages ready to deploy
  CodeDeploy -- ec2 or on premise
  CodePipeline -- continous delivery service
  XRay -- debug, you can request trace and find root cause.
  Cloud 9 -- IDE environment, you can develop code inside AWS

--- 
BREAK
---
 7) Managment Tools *IMPORTANT*
  - CloudWatch
  - CloudFormation, all time, scripted infrastructure
  - CloudTrail -- recommend turning it on for all
  - Config -- monitors config of entire env, you can move time backwards and forwards across time. Snapshots
  - OpsWorks -- robust uses Chef and Puppet way of automating env. Way of configuring ENV
  - Service Catalog -- Manage a catalog of IT services






## AWS IAM
create user
  access key and secret access key
    can only be used when programatically interatcing with aws
    cant use it to log into console
  
Access key ID
Secret access key 

programatically interacting with aws


Roles
  way to grant permission to entities you trust
  grant them a role so they can spin up instsnces, or write to bucket

ec3 instances to store files on s3


## S3

place to store your files in the cloud
  founder of dropbox -- designed simple webpage to interact with s3
    store data in s3
  
object-based storage
  video, photo, word docs,
  flat files


blocked-based
  where you install an os

you don't install os
designed to withstand failure
  spread across multiple areas

### Cloud beary labs
  you can see it stored
  0 bytes to 5 tb in size
  unlimmitted storage
  
  ### Files
    stored in buckets (folders)

S3 is universal namespace
  names must be unique globally
  when you make a bucket it makes a dns address
  s3-eu-west-1.amazonws/[name]

  s3-[region].amazon.aws

upload a file to s3 you will get a 200 code if upload success

## Data Consistency Model for S3
Read after Write consistency for PUTS of new Objects
  - you can read it straight away
  - you can read the text file available

Eventual Consistency for overwrite PUTS and DELTES (can take some time to propogate)
  - updating or deleting, it can take time to update

updates to s3 are automic
  you either get new or old data, never partial or corrupted data

s3 simple key-value store
  key
  value
  version id
  metadata (things you are storing, date last updated, etc)

s3 object
  key == filename
  s3 designed to be lexigraphical ()
  performance bottle necks
    adding something to beginnings of filenames
  
  value == data (bytes)
  version id
  subresources
    access control lists <-- fine grain permissions
    torrent

built for 99.9% SLA amazon gaurantee
  amazon 11 x 9s durabiliy (99.9...9 x 11)
  tiered storage available
  lifecycle management
  versioning
  encryption (several different ways)
  **secure data using access control lists and bucket policies**

## classes
  s3 - 9x11 durability, loss of 2 facilities concurrently
  s3 - IA (infrequently accessed) data accessed less frequently, but requires rapid access when needed
    lower then s3 but you are charged a retrieval fee
  reduced redunandcy storage -- only 99.99% durable
    alot cheaper than standard s3. Data you can generate again
    thumbnails RRS, can be made here (only 1 concurrent facility fault tolerance)
  ### glacier
    very cheap, data archival. 3-5 hours to restore from glacier
    1cent per gig

# S3 charges
  charged for
  storage
  requests
  storage management pricing -- tags, 
  data transfer pricing -- data into s3, but moving it around (replication) charged for that
  transfer acceleration (cloud front gloablly distributed edge )


## EXAM TIPS s3
object based, no os on it (only files)
  0 -- 5Tb
  unlimited storage
  Files are stored in buckets
  s3 is universal namespace
s3-[region].amazonaw.com/[bucketname]

Read after write consistency for PUTS of new Object
Eventual Consistency for overwrite PUTS and DELTES (some time to propogate)

s3 tiers
  s3
  s3 -IA
  s3 - RRDS (thumnails)
  glacier... 3-5 hours for accessing

key, value, versiin id, metadata, subresources (ACL, torrent)
no db or os on it

## READ S3 FAQ
  read the s3 FAQ alot!

min size for s3 is 0 bytes

versioning has MFA -- to delete, used tom provide addtional security

## LAB
infrequent access because it is a backup device

Exam tips
- versioning must be enabled on both source and destination buckets
- files NOT replicated automaticalkly, you cannot use daisy chaining or replicate to multiple biuckets at this time (need to run cli to copy over buckets)
- delete markers are replicated
- deleting individual versions or delete markers will not be replcated
- understand cross region replication at a high level
- use source and destination bucket
  -- easiest way to do it

VERY SAFE AND SECURE
  to save crypto currency


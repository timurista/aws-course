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






AWS IAM
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



## CDN
website in UK serving to whole world
requests to UK, longer latency than someone in South America

without CDN, they want webpage they have to go directly to UK pull down then bring back

CloudFront

Edge Location, location where content will be cached
  diff from AWS Region/AZ (Area Zone)

Origin -- all files that CDN will distribute
  s3 bucket, elb or route 53, ec2 instance

Distribution
  CDN with collection of Edge Locations

## CDN
How does it work?
  multiple users in multiple countries

Edge locations
  request goes to edge location, distribution URL
  caches it in ttl
  it's not quicker for first user, but second user it takes alot less time
    speeds up delivery of content
    rest of users can access it alot quicker
    can be used to deliver entire website
      requests for content routed to nearest edge location
  
  optimized to work with s3 simple storage
  EC2, Elastic Load Balancer
  works seemless wtih non-aws origin server, which stores the original, definitive version of your files

  Key terminology
    - Web Distribution (websites)
    - RTMP - Media Streaming (flash, adobe)
    - Edge Location (where content will be cached)
    - Origin (origin of files CDN wil be distributng, EC3, Rout53, S3 Bucket)
    - Distribtion - CDN which consists of collection of Edge Locations
    - Web Distribution - website
    - REMP - used for media streaming
    - Edge locations are not just READ only, you can write to them (put an object), which are then pushed back to origin
    - TTL, time to live, objects will be cached for that long
    - you can clear cached objects, but you will be charged

CloudFront Distribution
  Users can do get, head, options, put, post, patch, delete
  (you can do post, patch and delete)

default TTL is cached at edge location for 1 day (86400)

Restrict URL
  training company you want to distribute to employees
  you need to restrict so only certain employess
    use signed cookies
  
  CNAME
    cloudfront, really unfriendly url
      you can use

## Securing Your buckets
  By default all newly created buckets are PRIVATE
  - Bucket Policies
  - Access Control Lists
  S3 buckets configured to create access logs which log all requests made to s3 bucket

## Encryption
  4 methods for s3 (know this)
  - Intransit (info to and from bucket, )
    SSL/TLS <-- https
  - Data at Rest
    server side encryption
    client-side 
      - S3 managed keys, sse-s3 key is encrypted with rotated master key
        aes256 advanced standard 256
        you click on object and hit encrypt
      - AWS Key Mangement Service, Managed Keys -- SSE-KMS
        Envelop Key, added protection against unath access in s3
        audit trail of who was using keys
        transparency who is decrypting what, when
        default key you can use
      - Server Side Ecryption With Customer Provided Keys -- SSE-C, managment of key is done by you

      - Client Side Ecryption
        you upload it on your side then upload the encrypted files


## Storage Gateway
cost effective storage
  data center --> storage gateway
  async replicate up to aws s3, and to glacier
  vm you install on hose VMware ESXi or Microsoft HyperVi

3-4 different type
  File Gateway (NFS) flat file, word files, pdfs, etc
  Volumes Gateway (iSCSI), virtual hard disk, mysql server, using block based storage
    - stored volumes
    - cached volumes -- only most recent
  Tape Gateway (VTL)
    virtual tapes to S3, lifecycle policies off to glacier

Gateway Virtual Storge (Tage Gateway)

File Gateway
  store files in s3
  server --> (NFS) Storage Gateway
  connects in through s3, Direct Connect (business), AMazon VPC (virtual data center, server gateway sitting inside an amazon vpc)

  --> Amazon S3 -> AMazon S3-IA -> Amazon Glacier
  flat files, then do lifecycle management policies

## Volume Gateway
  isCSCI (i scuzzy) block-based protocol, virtual hard disk async backed up as snap shots, stored in cloud as ebs snapshots
    - stored volumes (entire copy local, data written to this is stored on your own stuff, storage gateway backs this up as ebs snaps, incremental)
    - 1gb -- 16tb in size
    - vritual harddisk, complete copy on site, backed up incrementally
    - Cached Volumes
      -- you only keep most recently read data on prem, rest is stored on s3, 32tb can be stored
      -- retains recently read
      - most recently read is stored on premise

## Tape Gateway
  you can use existing tape virtual tape cartridges on you gateway
    supported by backup exec, veam, etc

Exam tips
  File Gateway -- flat files
  Volume Gateway (block-based storage)
    stored volumes (media company don't want to keep it all time, or need fast latency)
    cached volumes
  gateway virtual tape library
    veeam, netbackup



# EC2
Linux instances by the second (on demand)
- by the hour (or note that has this been updated)

- Reserved - provide you capacity for reservation and significant discounts 1-3 year terms
- Spot -- rate, can go up and down depending on supply and demand.
  - spot price affected by how many people want to use that service
  - set bid price, what you are willing to pay by hour or by second
  - if spot brice < bid price, you will provision instances
  - instances above spot
- Dedicated Hosts -- physical ec2 server for software licenses, oracle or vm ware, or govt customers

## On Demand
  - Users want the low cost and flexibility of ec2 without upfront payment
  - unpredictable workloads cannot be interrupted
  - apps developed or tested on ec2 for first time

## Reserved (RI = reserved instance)
  - steady state or predictable usage (always 15 gigs ram)
  - users make upfront payments
  - STANDARD RI (75% off on demand)
  - CONVERTABLE RI (54% off demand up to) change attributes of RI as long as exchange results in creation of Reserved instances of equal or greater value
    - windows to linux pc, etc, or cpu optimized, etc.
    - you have to spend same or more if you go to Reserved Instances
  - SCHEDULED RI, schedule fraction of day or week within time windows you reserve. You can match capacity reservation to recurring schedule

## Spot
  - Insurance companies 3am sunday morning, spot price very low
  - Dat crunching or users

## Dedicated Host
  - Licensing
  - regulatory reqs for mult-tenant virtualiation
  - rservation for up to 70% off on demand price

# Families
D2 - Dense Storage FIles/Data Warehousing/Hadoop
R4 - Memory Optmized/Memory Intensive Apps/Dbs (R for RAM)
M4 - General Purpose / Application Servers (M, app, default MAIN CHOICE)
C4 - Cpu intensive, CPU instensive apps/dbs
G2 - Graphics intensive / video encoding, 3d app streaming
I2 - High Speed Storage / NoSql Dbs, Data Warehousing etc (I === SPEED)
F1 - Field Programmable Gate Array -- Hardware acceleration for your code (you can change hardware to suit software underneath)
T2 - Lowest Cost, general purpose / Web Servers / small dbs
P2 - Graphics/General Purpose GPU / Machine Learning, Bit Coin Mining etc
X1 - Memory Optimized / SAP Xtreme RAM

DIRTMCGFPX
I === IOPS
R === RAM
T2 Micro (cheap)
M == MAIN CHOICE
C == Compute
G == Graphics

DR Mc GIFT PX
P (graphics == PX)

10 instance types


# EBS
### IOPS is input output operations per second

General purpose SSD (GP2)
  block-based storage
  both price and performance
  - ration of 3 IOPS per GB with up to 10,000 IOPS and ability to burst up to 3000 IOPS for extneded periods of time for volumes at 3334 GiB and above
  - **boot volume**

Privisioned IOPS SSD (IO1)
  - IO intensive or NoSQL db
  - more than 10,000 IOPS
  - with these you can go up to 20,000 IOPS per second
  - **boot volume**

THroughput Optimized HDD (ST1)
  - Big Data
  - Data warehouses
  - Log processing
  - **NOT boot volume**

COld HDD (SC1)
  - lowest cost storage for infreq accessed workloads
  - File Server
  - **NOT boot volume**

Magnetic (Standard)
- lowest  per Gib of all EBS volume types that is **boot volume**, data access is infrequent

2 lowest cost options
- Cold HDD -- not bootable
- Magnetic -- bootable

---
Upcoming
===
Launch EC2 instance
clowd watch
aws command line
IAM roles with EC2
Bootstrap Scripts
Launc Config Groups
Autoscaling 101 <-- game changer for cloud
EFS (elastic file system)
Lambda Concepts
serveress webpage with lambda and api gateway
serverless website with polly
Build an alexa skill to help you study (read notes for you)
HPC (High Performance Compute)
---

What to know?
On Demand
Spot
  If you terminate isntance, you pay for that hour
    you are half hour in you pay
  If AWS terminates because bid price goes above what you want, you will get that hour for free

Reserved
Dedicated Hosts

EBS
  SSD General Purpose GP2 < 10,000
  SSD< Provisioned IOPS - IO1 > 10,000
  -- 
  ## not bootable
  HDD Throughout Otpmized ST1 - freq accessed workloads
  HDD Cold SC1 -- SC1 - less freq accessed data
  HDD Magnetic - cheap infreq accessd

You cannot mount 1 EBS volumne to multiple EC2 instances instead use EFS (for shared storage)

Types
DR - Dense storage, RAM (storage freq access)
MC - Main, Compute (big data)
GIFT - Graphics, IOPS (fast throughout put crunching), Field Gateway Array, T cheap websites
PX - P2 bitcoin or gpu (graphics), xtreme, best of all

## DEMO
one subnet = one availability zone
yum httpd -y // apache red hat server

## System Check Status
checks and makes sure hyperviser is up,

## Instance Status Check
you can reboot and itll come up on another hyperviser or terminate instance

you cannot encrypt the default device provided by amazon


## Key Points
Termination prevention is turned off by default
  -> turn on by clicking that check box
  - EBS backed instace root is deleted then instance terminated

you can encrypt root device using 3rd party software but not 

chkconfig httpd on <-- always starts when we reboot

## NOTE
any rule you make to a security group is instant
fixing security group is immediate


## Security groups are stateful
Outbound deleting rules means you can still access
<-- doesnt matter you have no outbound rules, the inbound rules like http will be allowed outbound as well

STATEFUL!

Network access control groups are different, they are statelss

Everything is blocked by default, I cant explicity block
only allow

RDP TCP 3389
MYSQL/Aurora TCP 3306

all inbound traffic is blocked by default
all outbound traffic is allowed
  changes to security groups take effect immediately
  multiple security groups with instances

Security groups are stateful
inbound rule ==> traffic is automatically allowd back out again

Network access control groups are stateless
  you can specify allow rules NOT deny rules

## EBS
hard disk drive has to be in same location as cpu, always have to have ebs volume and ec2 instance is same
amazone machine image gp2, we can upgrade to provision IO

Standard we can't modify the volume
  everything but normal magnetic storage

ec2 instance in west eu
take snapshot of ec2 instance (5 minutes)
  create image or another volume from it
  we can change colume type from ssd gp2
  to move ebs volumes from one to another you make a snapshot then from that snapshot I can **copy**
    to another region anywhere in the world
  
  ec2 instance from one region to another, copy and create image
    book from ec2
    images from backup
    AMI images
      -- no valid instance type
    
    TO make amazone machine image
      - instance, action > create image
      only of 1 ebs volume
      click Launch then you can do all different instance types

  
## EXAM TIPS
volumes and snapshots
- volumes exist on EBS
  virtual hard disk
  this is your c drive, root ~/
- snapshots are on s3
  - point in time copy of volumes
  snapshots are incremental, only blocks changed are moved to s3
  - snapshots can take some time to create
  - stop instance whil
  AMAZON MACHINE INSTANCES
    ami from snaps
  
  you can change ebs volume, size and storage time on the fly
  best practice is to stop it
    same availability zone as ec2 instance

to move an ec2 volume from one AZ/Region to another --> take an snap or image of it, then copy it to the new AZ/Region

snapshots are encrypted automatically
  DO THIS LAB AGAIN
  4-5 or 6 questions of moving
  this and VPC are crucial

DO AGAIN

RAID = Redundant Array of Indepndent Disks
  - RAID 0 - Striped No Redundancy

Snapshots of Root Device Volumes
- To create a snapshot for Amazon EBS volumes that serve as root devices stop instance
- snaps encryptied automatically
- volumes restored from snaps are encrypted
- you can sare snaps but only if unencrypted
- these snaps can be shared with other aws accounts made public

you can make snap of base image and promote to be machine image so next time you provision you dont need to do it again

AMI from snapshot is important

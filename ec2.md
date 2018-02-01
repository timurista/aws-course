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

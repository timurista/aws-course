## RDS Backups
automated backups
  daily snapshot and transaction logs in the day

retention period 1 - 35 days
  you can recover your db to any point in time, down to second
  automated backgroups take ful dails snapshot
  and transaction logs throughout the day

Friday 2:30 35 seconds, etc.
  enabled by default --> free storage equal to size
  defined window, (do this say 3am every morning)
  will get elevated latency

Snapshots done manually
  stored even after you delete RDS instance

Restored DB
  new RDS instance with new endpoint

Encryption data stored at rest
  KMS, read replicas, snaps, automated backups etc
  at present time, ecrypthing DB instance not supported
  you have to make new db instance and migrate stuff into it

Restore DB instance
  Point in time restoration
  full snapshot or point in time

Migrate to Aurora also, or new snapshot

You can copy and move to different region
  // restore to diff instance size and or class

Enable Encryption?
  master key
  once RDS is up and running, snaps and automatic backups
    take data from current db and import it
  Multi-AZ
  RDS -- RDS -- RDS -> US-EAST-1A -> US-EAST-1B, same dns endpoint if it fails it goes to EB

## Multi-AZ RDS
  automatic failover, it will goes to standby so things will restart quickly
  disaster recovery only, NOT for performance improvments.

  SQL Server
  Oracle,
  MySQL Server
  Postgres
  MariaDB

## Read Replica
Async replica copy where you can read from
  can use to boost performance
  read heavy workload
  instead of reading from one main db they can read from the other replicas
  -- you can scale out from main db
  up to 5 Read Replicas
    - use this for read intensive activities
        test  / dev purposes, read from copy not from prod db
    - async replication

Used for Scaling, NOT Disaster REcovery
  ElastiCache also for optimizing reading

you can have read replicas of read replicas
Each read replica have its own DNS end point
cannot have read replicas that have Multi-AZ
  you can create Read Replicas of Multi-AZ source db
Promoted to be their own DB


## Scaling RDS
not easy to scale up, you need bigger instance size or to add a read replica (only for reading)

## DynamoDB
automatic scaling, push putton scaling -- no down time. scales well

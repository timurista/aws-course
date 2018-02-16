# redShift
fast, powerful, datawharehouse
0.25 a month

figure out net profit
  - number of radios in EMEA
  - unit cost of each thing
  - sales price - unit cost

Single Node (160gb)
Multi-Node
  Leader Node (manages client connections and receives queries)
  Compute Node (store data and perform queries and computations) up to 128 compute nodes
  
Columnar data storage
  nulike row
  for analytics, aggregates over large data sets

When queries based on particular cols
  only data in sequentially based on particular cols
  less iops
  advanced compression for columnar

CDN
  stream by spreading over many compression techniques

## COmpression
  Samples data and selects most compression scheme
  Redshift can be really fast
  MPP

easy to add nodes to warehouse
can be 10 times faster

# Compute Nodes

3 node data warehouse 

## Redshift security
SSL
AES-256
HSM
or Aws Keys
not multi-az
  don't need it up
  management to run queries on
    can restore snapshots to new AZ
  fast and cheap
  Columnar storage -- speed, storing data sequentially

## ElasticCache
theoretical
  2 engines
  web service makes it easy to scale in memory cache in the cloud
    caches things, db --> online store, cache info and load off DB
    improves latency and throughput, media sharing, etc.
    compute intensive
    recommendation engines etc
    IO or computational
  Memcached -- widely adopted
  Redis -- open source key-value store, Master / Slave

  Exam tip
    stress or load
    elastic cache is good

## Aurora
  only runs on AWS infrastructure
  it is mysql compatible
  -- import there
  MySQL - challenge to oracle. advantages, high availability and performance
  


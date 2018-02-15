## DynamoDB
flexible noSQL db, milli latency at any scale
- docment and ke-value data modles

instagram on ios,
  the connect to dynamodb, lambda

## Developer Associate Course
3 distinct data centres -- across 3 diff facilities (availability zones?)
- eventually consistent reads
  1 second, best for read performance
- strongly conssitent reads
  - all writes, immediately available?
  - writes then reads

## Provision Capacity
  write --> 10 units
  Read --> 0.0065 for every 50 units

## Storage Costs
  0.25 gb per month

1 million writes and 1 million reads per day, storing 3gb of data
  calc writes and reads per second you need
  1 mil / 24 / 60 / 60 = 11.6 writes per second

write capacity unit handles 1 write per second, need 12 write capacity units

and also need 12 read capacity units
units billed in blocks of 10

0.0065/10 * 12 * 24 = 0.1872
0.0065/50 * 12 * 24 = 0.0374
  scalable and really good performance, no joins needed, run dynamoDB

## Create DynamoDB table
table acloudguru on sql
primary studentid
  - you can reserve capacity (1-3 yr capacity)
  - not sure how much read and write you want
  - dynamically add cols

DevOps course includes this




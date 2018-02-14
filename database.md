## Databases
DynamoDB
ElasticCache
Redshift
DMS (Managed  DB Migration Service)

Database, Tables, Row, Fields (cols)

Row 1 Record about me
  Field same type of data

RDBS
  SQL server
  oracle
  MariaDB (new)
  Aurora
  PostgresSQL

postgres and dynamo db come up alot
  figure out where to se one over other

NonRelational
  CoucheDB
  MongoDB
  DynamoDB <-- document-oriented

DB
  Collection === TABLE
  Document === ROW (record set)
  Key value pairs (FIELDS)

{
  "id": "4232",
  "surname": "Smith"
  address: [] ... <-- embedded
}

#Data Warehousing
Business inteligence, Reporting Services, Oracle Hyperion
Pull in large and complex data sets, current performance vs targets

VS RDS
online transaction
OLTP vs OLAP

OLTP <-- pulls up the DB, grabs thing
OLAP <-- analyze large information
  net profit over given time, sales price in each region, sales prices all diff, then sales price minus unit cost. Huge, hitting DB lots of diff qeries.
  SO RDBS hard to scale out

Copy of prod db, and you run OLAP on it
  uses columnar stoarge, order number, can imporve performance times

## Elasticache
Memcached,
Redis
  - diff scenarios, improve db performance speeds

cache most frequently requested (top 10 deals)
  gets it from

## DMS Database Migration Service
Migrate prod db onto aws automatically
  data, parallel transer, schema conversion tool
  you can convert source db to diff target db

cnvert to aurora, save quite a bit of money
  format compatible with mysql

legacy over to free open source db




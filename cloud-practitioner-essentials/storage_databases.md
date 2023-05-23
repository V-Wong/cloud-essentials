# Storage and Databases
## Instance Stores and Elastic Block Store
### Block Level Storage
**Block level storage** behaves like **physical hard drives**. It is a place to store files. When a file is updated, **only changed pieces need to be updated**.

### Instance Store
An **instance store** provides **temporary** block-level storage for an EC2 instance. It is disk storage that is **physically attached** to the **host computer** for an EC2 instance. When the instance is terminated, we **lose the data** in the instance store.
- This is because the **underlying host can change** when an EC2 restarts.

### Elastic Block Store (EBS)
**EBS** is a service that provides **persistent** block-level storage that can be used with EC2 instances. The data **remains available** if we stop or terminate an EC2 instance.

With EBS, we can take **incremental backups** by creating **snapshots**. In this backup strategy, subsequent backups only have the blocks of data that have **changed since the last snapshot**.

## Simple Storage Service (S3)
### Object Storage
In **object storage**, each object consists of:
- **Data**: any type of file.
- **Metadata**: information about the data, how it is used, the object size, etc.
- **Key**: unique identifier for the object.

When a file in object storage is modified, the **entire object is updated**.

### Amazon Simple Storage Service (S3)
**S3** provides object-level storage and stores all data as objects in buckets (similar to directories).

When we upload a file to S3, we set **permissions** to control visibility and access. We also use S3 versioning to **track changes** to an object over time.

#### Storage Classes
S3 has different **storage classes** to fit our business needs. When selecting a storage class, we consider:
- How **often** we plan to retrieve the data.
- How **available** we need the data to be.

The storage classes offered are:
- **Standard**:
    - **High availability**.
    - Good for wide range of use cases.
- **Standard-Infrequent Access**: 
    - Similar to Standard but has **lower storage price** and **higher retrieval price**.
    - Ideal for infrequently accessed data.
- **One Zone-Infrequent Access**: 
    - Stores data cheaply in a **single AZ**. 
    - Ideal for cost savings or if the data can be reproduced easily during an AZ failure.
- **Intelligent-Tiering**: 
    - Automatically **moves object** between Standard and Infrequent Access tiers depending on access patterns. 
    - Requires a small monthly monitoring price and automation feed per object.
    - Ideal for data with unknown or changing access patterns.
- **Glacier Instant Retrieval**: 
    - Works well for **archived data** that require **immediate access**.
    - Can retrieve objects within a few seconds.
- **Glacier Flexible Retrieval**:
    - Low-cost data **archiving**.
    - Can retrieve objects within minutes to hours.
- **Glacier Deep Archive**: 
    - Lowest-cost data **archiving**.
    - Able to retrieve objects within 12 hours.
- **Outposts**: 
    - Creates S3 buckets on S3 Outposts. 
    - Makes it easier to retrieve, store, and access data on Outposts.

### Comparing EBS and S3
S3 has the following benefits:
- **Web enabled**: every object has a URL that we can control viewing and management rights.
- **Regionally distributed**: extremely durable; no need to worry abut backup strategies.

EBS has the following benefits:
- **Block storage**: allows for delta updates instead of re-uploading full files when a file changes.

## Elastic File System (EFS)
### File Storage
In **file storage**, multiple clients access data stored in **shared file folders**. Here, a **storage server** uses block storage with a local file system to organise files. Clients access data through file paths.

Compared to block storage and object storage, file storage is ideal when a **large number of services** need to access the data at the **same time**.

### Amazon Elastic File System
**EFS** is a scalable file system used with AWS cloud services and on-prem resources.

### Comparing EBS and EFS
EBS volumes store data in a **single AZ**. To attach an EC2 instance to an EBS volume, both the instance and volum must reside **within the same AZ**.

EFS is a **regional service**. It stores data in and across **multiple AZ**. The duplicate storage enables us to access data **concurrently from all the AZs** in the region where a file system is located.

## Relational Database Service (RDS)
### Relational Databases
In a **relational database**, data is stored in a way that **relates** to other pieces of data. Relational databases use **SQL** to store and query data.

### Amazon Relational Database Service (RDS)
**Amazon RDS** is a service that enables us to run relational databases in the AWS cloud.

Amazon RDS is a **managed service** that automates:
- Hardware provisioning.
- Database setup.
- Patching.
- Backups.

Amazon RDS also provides a number of **security options**. Many Amazon RDS database engines offer:
- **Encryption at rest**: protecting data while it is stored.
- **Encryption in transit**: protecting data while it is being sent and received.

### Amazon Aurora
**Amazon Aurora** is an enterprise-class relational database. It is compatible with MySQL and PostreSQL. It is up to 5x faster than standard MySQL databases and up to 3x faster than standard PostgreSQL databases.

Amazon Aurora helps reduce database costs by reducing unnecessary IO operations, while ensuring database resources remain reliable and available.

Amazon Aurora should be considered if the workload requires **high availability**. It replicates 6 copies of our data across 3 AZs and continuously backs up our data to S3.

## Amazon DynamoDB
### Non-Relational Databases
**Non-relational databases** use structures other than rows and columns to store data. One common structure type is **key-value pairs**. In a key-value database, not every item in the table has to have the same attributes.

### Amazon DynamoDB
**Amazon DynamoDB** is a **key-value** database service that delivers **single-digit millisecond performance** at any scale. Features of Amazon RDS include:
- **Serverless**: we do not have to provision, patch or manage servers. We also do not have to install, maintain or operate software.
- **Auto-scaling**: DynamoDB automatically scales to adjust for changes in capacity while maintaining consistent performance.

## Amazon Redshift
### Data Warehouses
**Data warehouses** are large and centralised repositories of structured, organised, and integrated data collected from **various sources** within an organisation. They are designed for **historical analytics** (e.g. business intelligence) rather than **operational analysis**.

### Amazon Redshift
Redshift is Amazon's **data warehousing as a service**. It can be used for **big data analytics** and offers the ability to collect data from many sources to help us understand relationships and trends across data.

## AWS Database Migration Service (AWS DMS)
**AWS DMS** enables us to **migrate** relational databses, non-relational databases, and other types of data stores.

With AWS DMS, we move data between a **source database** and a **target database**. The source and target databases can be of the same or different types. During the migration, the source database remains operational.

Use cases of AWS DMS include:
- **Development and testing**: enable developers to test applications against production data without affecting production users.
- **Database consolidation**: combining serval databases into a single database.
- **Continuous replication**: sending ongoing copies of our data to other target sources instead of doing a one-time migration.

## Other Database Services
Lesser known AWS database services include:
- **DocumentDB**: for MongoDB workloads.
- **Neptune**: graph database.
- **ElastiCache**: caching layer ontop of database.
- **DynamoDB Accelerator**: in-memory cache for DynamoDB.

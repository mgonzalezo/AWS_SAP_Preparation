# Amazon Aurora

- It is recommended to use Aurora Serverless for lightly-used applications, with peaks of 30 minutes to several hours 
a few times each day or several times per year, such as human resources, budgeting, or operational reporting application.
- Aurora can store up to 128 TB of data. Unless the database engine version is different, schema conversion is not required.
- Aurora  can scale the replicas as needed.

## Amazon Aurora Global Database

- Designed for globally distributed applications, allowing a single Amazon Aurora database to span multiple AWS regions
Replicates your data with no impact on database performance, enables fast local reads with low latency in each region
- Provides disaster recovery from region-wide outages.
- Uses storage-based replication with typical latency of less than 1 second
- Unlikely event of a regional degradation or outage, one of the secondary regions can be promoted to read and write capabilities in less than 1 minute.
- Typical cross-region replication latencies below 1 second
- If your primary region suffers a performance degradation or outage, you can promote one of the secondary regions to take read/write responsibilities.
- Effective Recovery Point Objective (RPO) of 1 second and a Recovery Time Objective (RTO) of less than 1 minute,

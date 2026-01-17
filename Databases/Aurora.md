# Amazon Aurora

- MySQL and PostgreSQL-compatible relational database built for the cloud.
- Up to 5x faster than standard MySQL, 3x faster than standard PostgreSQL.
- Recommended for lightly-used applications with Aurora Serverless: peaks of 30 minutes to several hours a few times each day or year (HR, budgeting, operational reporting).
- Aurora can store up to 128 TB of data per database cluster.
- Unless the database engine version is different, schema conversion is not required for migrations.
- Can scale read replicas as needed (up to 15 read replicas).
- Automatic failover to read replica in under 30 seconds.

## Amazon Aurora Global Database

- Designed for globally distributed applications, allowing a single Amazon Aurora database to span multiple AWS regions.
- Replicates data with no impact on database performance.
- Enables fast local reads with low latency in each region.
- Provides disaster recovery from region-wide outages.
- Uses storage-based replication with typical latency of less than 1 second.
- In unlikely event of regional degradation or outage, secondary region can be promoted to read and write capabilities in less than 1 minute.
- Typical cross-region replication latencies below 1 second.
- Effective Recovery Point Objective (RPO) of 1 second and Recovery Time Objective (RTO) of less than 1 minute.
- Supports up to 5 secondary regions.

## Blue/Green Deployments for Aurora Global Database (2025)

- Safer, simpler, and faster updates for Aurora Global Databases.
- Create staging (green) environment that mirrors production (blue) Aurora Global Database.
- Includes primary and all secondary regions in the staging environment.
- Perform critical database operations with minimal downtime:
  - Major and minor version upgrades.
  - OS updates.
  - Parameter modifications.
  - Instance type changes/validations.
  - Schema changes.
- Automated switchover from blue to green environment.
- Rollback capability if issues detected.

## AWS Organizations Integration (2025)

### Upgrade Rollout Policy

- Control automatic minor version upgrades across multiple accounts and databases.
- Eliminates operational overhead of coordinating upgrades manually or with custom tools.
- Test upgrades in less critical environments before rolling out to production.
- Centralized management across hundreds of resources and accounts.
- Ensures peace of mind by validating upgrades progressively.

### Supported Database Engines

- Aurora MySQL-Compatible Edition.
- Aurora PostgreSQL-Compatible Edition.

## Aurora PostgreSQL Enhancements (2025)

### PostgreSQL 18.1 Support (Preview)

- PostgreSQL 18.1 available in RDS Database Preview Environment.
- **Skip scan** support for multicolumn B-tree indexes.
- Improved WHERE clause handling for OR and IN conditions.
- Better query optimization for complex predicates.

### Performance Improvements (2025)

- Aurora storage metadata initializes more quickly during unplanned failovers and server restarts.
- Reduced overall downtime during recovery scenarios.
- Enabled support for FIPS-validated cryptography (fully owned AWS implementation).

## Aurora MySQL Enhancements (2025)

### Performance Optimizations

- Improved parallel export performance by optimizing bootstrap process for large volumes (>64 TB).
- Reduces overall export operation time significantly.
- New global variable `aurora_lambda_request_timeout` to configure AWS Lambda request timeouts (default: 10 seconds).
- Improvements that reduce DB instance restart time during:
  - Database restarts.
  - Patch or minor version upgrades.
  - Failovers.

### Compatibility

- Compatible with MySQL 8.0.39, 8.0.42, 8.0.43 (multiple versions available 2025).

## Aurora Serverless v2

- Instantly scales to hundreds of thousands of transactions per second.
- Scales in fine-grained increments (0.5 ACU minimum).
- Scales to zero when idle (only v1 supports this fully).
- Pay only for resources consumed.
- Compatible with existing Aurora features (Global Database, read replicas).

## Storage and Backup

- Storage automatically grows in 10 GB increments up to 128 TB.
- 6 copies of data across 3 Availability Zones.
- Continuous backup to S3 (automatic, no performance impact).
- Point-in-time recovery (PITR) to any second within retention period.
- Backup retention: 1 to 35 days.
- Automated backups cannot be disabled.

## High Availability

- Data replicated 6 ways across 3 AZs.
- Can lose 2 copies for writes, 3 copies for reads without data loss.
- Self-healing storage with continuous scanning for errors.
- Automatic failover to read replica in less than 30 seconds.
- Read replicas can be used as failover targets.

## Performance Features

- Up to 15 read replicas (Aurora Replicas) with sub-10ms replica lag.
- Custom endpoints for load balancing specific workload types.
- Parallel query for faster analytical queries on current data.
- Aurora Machine Learning integration (SageMaker, Comprehend).

## Security

- VPC isolation.
- Encryption at rest using KMS (AES-256).
- Encryption in transit using SSL.
- Automated backups, snapshots, and replicas encrypted if source encrypted.
- IAM database authentication.
- Integration with AWS Secrets Manager for credential rotation.

## Monitoring

- CloudWatch metrics for performance monitoring.
- Enhanced Monitoring for OS-level metrics.
- Performance Insights for query-level analysis.
- Database Activity Streams for compliance and auditing.

## Exam Tips

- Aurora stores up to 128 TB per cluster, automatically grows in 10 GB increments.
- Aurora Global Database has RPO of 1 second, RTO of less than 1 minute.
- Blue/Green Deployments (2025) allow safe updates for Global Databases with minimal downtime.
- Upgrade Rollout Policy (2025) centralizes version upgrade management across AWS Organizations.
- 6 copies of data across 3 AZs - can lose 2 copies for writes without data loss.
- Automatic failover to read replica in under 30 seconds.
- Aurora Serverless v2 scales instantly in fine-grained increments (0.5 ACU).
- Compatible with MySQL and PostgreSQL - use standard drivers and tools.
- Automated backups enabled by default (cannot disable) with 1-35 day retention.
- Performance Insights provides query-level performance analysis.
- PostgreSQL 18.1 (2025) includes skip scan for multicolumn indexes.
- Aurora MySQL (2025) improved parallel export and reduced failover time.


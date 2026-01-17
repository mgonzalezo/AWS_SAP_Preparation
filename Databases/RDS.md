# Amazon RDS

- Managed relational database service supporting multiple engines.
- Automated backups, patching, and monitoring.
- Multi-AZ deployment for high availability.
- Read replicas for read scalability.

## Supported Database Engines

- Amazon Aurora (MySQL and PostgreSQL-compatible).
- MySQL.
- PostgreSQL.
- MariaDB.
- Oracle.
- Microsoft SQL Server.
- IBM Db2.

## Important Limitations

- **Oracle RAC is not supported by RDS** - use Oracle on EC2 for RAC.
- DB2 is supported by RDS (all IBM Websphere products supported by AWS).
- Oracle Real Application Clusters (RAC) One Node provides virtualized servers on single machine.
- MySQL does not support auto scaling for read replicas.
- No automatic promotion of read replica in backup region as master database.
- When promoting read replica, RDS instance will reboot.
- Can promote read replica directly to standalone DB instance (no snapshot needed).

## RDS Storage Enhancements (2025)

### Increased Storage Capacity

- **RDS for SQL Server**: Increased from 64 TiB to 256 TiB (4x increase).
- **RDS for Oracle**: Increased from 64 TiB to 256 TiB (4x increase).
- 4x improvement in IOPS performance.
- 4x improvement in I/O bandwidth.

### RDS for SQL Server Optimize CPUs (2025)

- Reduce costs by up to 55% by optimizing CPU core count.
- Useful for SQL Server licensing (licensed per core).
- Maintain same memory and storage while reducing cores.

## AWS Organizations Integration (2025)

### Upgrade Rollout Policy

- Control automatic minor version upgrades across multiple AWS accounts.
- Eliminates operational overhead of manual coordination across hundreds of resources.
- Test upgrades in less critical environments before production rollout.
- Centralized management for compliance and consistency.

### Supported RDS Engines

- RDS for MySQL.
- RDS for PostgreSQL.
- RDS for MariaDB.
- RDS for SQL Server.
- RDS for Oracle.
- RDS for Db2.

## Amazon RDS storage types

- General Purpose SSD (also known as gp2), Provisioned IOPS SSD (also known as io1), and magnetic (also known as standard)

- You can create MySQL, MariaDB, Oracle, and PostgreSQL RDS DB instances with up to 64 tebibytes (TiB) of storage. You can create SQL Server RDS DB instances with up to 16 TiB of storage. For this amount of storage, use the Provisioned IOPS SSD and General Purpose SSD storage types.

  - General Purpose SSD – General Purpose SSD volumes offer cost-effective storage that is ideal for a broad range of workloads. These volumes deliver single-digit millisecond latencies and the ability to burst to 3,000 IOPS for extended periods of time. Baseline performance for these volumes is determined by the volume's size.

  - Provisioned IOPS – Provisioned IOPS storage is designed to meet the needs of I/O-intensive workloads, particularly database workloads, that require low I/O latency and consistent I/O throughput.

  - Magnetic – Amazon RDS also supports magnetic storage for backward compatibility. We recommend that you use General Purpose SSD or Provisioned IOPS for any new storage needs. 

<p align="center">
  <img alt="alt text" src="GP1.png" width="400">
  <br>
    <em>General Purpose SSD Storage. Source: https://digitalcloud.training/</em>
</p>
</n>
</n>
<p align="center">
  <img alt="alt text" src="IO1.png" width="400">
  <br>
    <em>Provisioned IOPS SSD Storage. Source: https://digitalcloud.training/</em>
</p>
</n>
</n>
<p align="center">
  <img alt="alt text" src="MAG1.png" width="400">
  <br>
    <em>Magnetic Storage. Source: https://digitalcloud.training/</em>
</p>
</n>
</n>

## Troubleshooting Scenario

**Scenario**: Amazon CloudWatch DiskQueueDepth metric for the DB instance increases suddenly during peak usage periods.
**Solution**: Double the amount of I/O that DB instance can handle
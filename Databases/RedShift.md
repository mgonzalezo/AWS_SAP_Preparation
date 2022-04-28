# Amazon Redshift

- Automated snapshots are enabled for a cluster, periodically takes snapshots of that cluster, usually every eight hours or following every 5 GB per node of data changes
- Automated snapshots are enabled by default when you create a cluster
- These snapshots are deleted at the end of a retention period (24H by default).
- You can enable Amazon Redshift to automatically copy snapshots to another region 
  - Specify the destination region where you want snapshots to be copied. 
  - In the case of automated snapshots, you can also specify the retention period that they should be kept in the destination region. 
- Redshift is primarily used for OLAP scenarios whereas RDS is used for OLTP scenarios.
- Amazon Redshift only has cross-region backup feature (using snapshots); it can’t replicate directly to another cluster in another region
- Amazon Redshift workload management (WLM) enables users to flexibly manage priorities within workloads so that short, fast-running queries won’t get stuck behind long-running queries. 
- With manual WLM, Amazon Redshift configures one queue with a concurrency level of five, which enables up to five queries to run concurrently, plus one predefined Superuser queue, with a concurrency level of one.
- You can define up to eight queues. Each queue can be configured with a maximum concurrency level of 50. The maximum total concurrency level for all user-defined queues (not including the Superuser queue) is 50.

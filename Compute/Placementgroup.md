# Placement Group

- When you launch a new EC2 instance, the EC2 service attempts to place the instance in such a way that all of your 
- Instances are spread out across underlying hardware to minimize correlated failures. You can use placement groups to influence the placement of a group of interdependent instances to meet the needs of your workload. 
- Depending on the type of workload, you can create a placement group using one of the following placement strategies:
  • **Cluster** – packs instances close together inside an Availability Zone. This strategy enables workloads to achieve the low-latency network performance necessary for tightly-coupled node-to-node communication that is typical of HPC applications.
  • **Partition** – spreads your instances across logical partitions such that groups of instances in one partition do not share the underlying hardware with groups of instances in different partitions. This strategy is typically used by large distributed and replicated workloads, such as Hadoop, Cassandra, and Kafka.
  • **Spread** – strictly places a small group of instances across distinct underlying hardware to reduce correlated failures.
- There is no charge for creating a placement group. Charges are applied once EC2 instances are deployed.

# AWS SAP Preparation

Repository for AWS Solution Architect Professional exam preparation, including theory and practice (hands-on labs).
Chapters have been categorized based on latest [AWS Solutions Architect Guideline.](https://d1.awsstatic.com/training-and-certification/docs-sa-pro/AWS-Certified-Solutions-Architect-Professional_Exam-Guide.pdf)



- [AWS SAP Preparation](#aws-sap-preparation)
  - [Reference Materials](#reference-materials)
    - [Application _Integration](#application-_integration)
      - [AWSOpworks](#awsopworks)
      - [SQS](#sqs)
    - [Billing_Cost_Mgmt](#billing_cost_mgmt)
      - [AWS_Cost_Usage_Report](#aws_cost_usage_report)
    - [Compute](#compute)
      - [AWS_ECS](#aws_ecs)
        - [Task_definitions](#task_definitions)
      - [ELB](#elb)
        - [Application Load Balancer:](#application-load-balancer)
      - [Placement Group](#placement-group)
    - [Databases](#databases)
      - [Amazon_Neptune](#amazon_neptune)
      - [Amazon_Aurora](#amazon_aurora)
        - [Amazon_Aurora_Global_Database](#amazon_aurora_global_database)
      - [Caching Strategies](#caching-strategies)
      - [Amazon RDS](#amazon-rds)
        - [Amazon RDS storage types](#amazon-rds-storage-types)
        - [Troubleshooting Scenario](#troubleshooting-scenario)
      - [AWS DynamoDB](#aws-dynamodb)
        - [DynamoDB Accelerator](#dynamodb-accelerator)
        - [Global Tables:](#global-tables)
        - [DynamoDB conditional writes](#dynamodb-conditional-writes)
      - [Amazon Redshift](#amazon-redshift)
    - [Developer_tools](#developer_tools)
      - [AWS_CodeDeploy](#aws_codedeploy)
    - [End_user_Computing](#end_user_computing)
      - [AppStream2_0](#appstream2_0)
      - [AWS_WorkSpaces](#aws_workspaces)
    - [Machine_Learning](#machine_learning)
      - [Amazon Lex](#amazon-lex)
      - [Amazon Comprehend](#amazon-comprehend)
      - [Amazon Polly](#amazon-polly)
      - [Amazon Transcribe](#amazon-transcribe)
    - [Management_Goverment](#management_goverment)
- [The AWS Service Catalog](#the-aws-service-catalog)


## Reference Materials

Please find below the list of Referenced materials for this Guide. I have included both free and paid resources used to create this material

1. Udemy - https://www.udemy.com/course/aws-solutions-architect-professional/
2. Tutorials Dojo - https://portal.tutorialsdojo.com/
3. AWS SA Professional Training - https://cloudacademy.com/
4. AWS Certified SAP Hands on - https://digitalcloud.training/
5. AWS Exam Readiness SAP - https://aws.amazon.com/certification/certified-solutions-architect-professional/
6. AWS WhitePapers - https://aws.amazon.com/whitepapers/
7. AWS Free practice questions - https://explore.skillbuilder.aws/


### Application _Integration

#### AWSOpworks

- Let you use Chef and Puppet to automate how servers are configured, deployed, and managed across
your Amazon EC2 instances or on-premises compute environments. 
- It can’t deploy AWS Lambda applications.
- AWS OpsWorks Stacks automatically installs the latest updates during setup, after an instance finishes booting. 
- AWS OpsWorks Stacks does not automatically install updates after an instance is online, to avoid interruptions such as restarting application servers. Instead, you manage updates to your online instances yourself, so you can minimize any disruptions.
- On Linux-based instances in Chef 11.10 or older stacks, run the Update Dependencies stack command, which installs the current set of security patches and other updates on the specified instances.


#### SQS

- Fully managed message queuing service that makes it easy to decouple and scale microservices, distributed systems, and serverless applications.
- To have compatibility with JMS or other protocols like MQTT AMQP, we use Amazon MQ
- You can use SQS to buffer and scale the backend service to accommodate the large incoming traffic. 
- You can save the submitted answers on the SQS Queue and then quickly return the user to a new page stating that the answers are successfully submitted. 
- This is a simple cost-effective design that improves user experience without increasing the capacity of your systems.
- SQS makes it simple and cost-effective to decouple and coordinate the components of a cloud application
you can send, store, and receive messages between software components at any volume, without losing messages or requiring other services to be available all the time
- An SQS queue cannot be used as a direct input for an AWS Step Function workflow.

### Billing_Cost_Mgmt

#### AWS_Cost_Usage_Report

- The most comprehensive set of AWS cost and usage data available, including additional metadata about: 
  - AWS services, pricing, credit, fees, taxes, discounts, cost categories, Reserved Instances, and Savings Plans.
- AWS delivers the AWS Cost & Usage Report to whichever Amazon Simple Storage Service (S3) bucket you specify during setup
- You can configure your Cost & Usage Reports to integrate with Amazon Athena.

### Compute

#### AWS_ECS

- You can register Spot Instances to your Amazon ECS clusters.
- Amazon EC2 terminates, stops, or hibernates your Spot Instance when the Spot price exceeds the maximum price for your request or capacity is no longer available
- Amazon EC2 provides a Spot Instance interruption notice, which gives the instance a two-minute warning before it is interrupted.
- ECS Spot Instance draining is enabled on the instance, ECS receives the Spot Instance interruption notice and places the instance in DRAINING status.
- Container instance is set to DRAINING -> Amazon ECS prevents new tasks from being scheduled for placement on the container instance
- Spot Instance draining is disabled by default and must be manually enabled by adding the line:
    ECS_ENABLE_SPOT_INSTANCE_DRAINING=true on your /etc/ecs/ecs.config file.
- The recommended best practice is to select the “Diversified” strategy, to maximize provisioning choices, while reducing the costs. 

##### Task_definitions

- Split into separate parts: the task family, the IAM task role, the network mode, container definitions, volumes, 
  task placement constraints, and launch types.
- The networking behavior of Amazon ECS tasks hosted on Amazon EC2 instances is dependent on the network mode defined in the task definition. The following are the available network modes. Amazon ECS recommends using the awsvpc network mode unless you have a specific need to use a different network mode.
  - **awsvpc**: The task is allocated its own elastic network interface (ENI) and a primary private IPv4 address. This gives the task the same networking properties as Amazon EC2 instances.
  - **bridge**: The task utilizes Docker's built-in virtual network which runs inside each Amazon EC2 instance hosting the task.
  - **host**: The task bypasses Docker's built-in virtual network and maps container ports directly to the ENI of the Amazon EC2 instance hosting the task. As a result, you can't run multiple instantiations of the same task on a single Amazon EC2 instance when port mappings are used.
  - **none**: The task has no external network connectivity.

#### ELB

##### Application Load Balancer:

- You can host multiple TLS secured applications, each with its own TLS certificate.
- In order to use SNI, all you need to do is bind multiple certificates to the same secure listener on your load balancer.
- ALB will automatically choose the optimal TLS certificate for each client. These features are provided at no additional charge.
- A wildcard certificate can only handle multiple sub-domains but not different domain names.
- SNI Custom SSL
  - Provides an efficient way to deliver content over HTTPS using your own domain and SSL certificate
  - Relies on the SNI extension of the Transport Layer Security protocol
  - Allows multiple domains to serve SSL traffic over the same IP address by including the hostname which the viewers are trying to connect to.
- ELB access logs will be delayed by at least 5 minutes before they arrive in Amazon S3

- In the ALB, you can create a listener that uses encrypted connections (also known as SSL offload). This feature enables traffic encryption between your load balancer and the clients that initiate SSL or TLS sessions.
- To use an HTTPS listener, you must deploy an SSL/TLS server certificate on your load balancer. The load balancer uses this certificate to terminate the connection and then decrypt requests from clients before sending them to the targets.
- Although you can terminate the SSL in the EC2 instance, this setup is not recommended in this scenario. It is best to store the SSL certificate in IAM or in AWS Certificate Manager (ACM) where you can control which teams, either the Security or the Development team, can have access.
- The clients access the website through the Load Balancer and not the EC2 instances directly. Using CloudHSM to store your SSL certificate will just increase your costs without satisfying the requirement.


#### Placement Group

- When you launch a new EC2 instance, the EC2 service attempts to place the instance in such a way that all of your 
- Instances are spread out across underlying hardware to minimize correlated failures. You can use placement groups to influence the placement of a group of interdependent instances to meet the needs of your workload. 
- Depending on the type of workload, you can create a placement group using one of the following placement strategies:
  • **Cluster** – packs instances close together inside an Availability Zone. This strategy enables workloads to achieve the low-latency network performance necessary for tightly-coupled node-to-node communication that is typical of HPC applications.
  • **Partition** – spreads your instances across logical partitions such that groups of instances in one partition do not share the underlying hardware with groups of instances in different partitions. This strategy is typically used by large distributed and replicated workloads, such as Hadoop, Cassandra, and Kafka.
  • **Spread** – strictly places a small group of instances across distinct underlying hardware to reduce correlated failures.
- There is no charge for creating a placement group. Charges are applied once EC2 instances are deployed.


### Databases

#### Amazon_Neptune

- Fast, reliable, fully-managed graph database service that makes it easy to build and run applications that work with highly connected datasets.
- The core of Neptune is a purpose-built, high-performance graph database engine.
- This engine is optimized for storing billions of relationships and querying the graph with milliseconds latency.

#### Amazon_Aurora

- It is recommended to use Aurora Serverless for lightly-used applications, with peaks of 30 minutes to several hours 
a few times each day or several times per year, such as human resources, budgeting, or operational reporting application.
- Aurora can store up to 128 TB of data. Unless the database engine version is different, schema conversion is not required.
- Aurora  can scale the replicas as needed.

##### Amazon_Aurora_Global_Database

- Designed for globally distributed applications, allowing a single Amazon Aurora database to span multiple AWS regions
Replicates your data with no impact on database performance, enables fast local reads with low latency in each region
- Provides disaster recovery from region-wide outages.
- Uses storage-based replication with typical latency of less than 1 second
- Unlikely event of a regional degradation or outage, one of the secondary regions can be promoted to read and write capabilities in less than 1 minute.
- Typical cross-region replication latencies below 1 second
- If your primary region suffers a performance degradation or outage, you can promote one of the secondary regions to take read/write responsibilities.
- Effective Recovery Point Objective (RPO) of 1 second and a Recovery Time Objective (RTO) of less than 1 minute,

#### Caching Strategies

- Lazy Loading – a caching strategy that loads data into the cache only when necessary.
  - Only requested data is cached.
  - Node failures are not fatal.
  - There is a cache miss penalty.
  - Stale data.
- Write Through – adds data or updates data in the cache whenever data is written to the database.
  - Data in the cache is never stale.
  - Write penalty vs. Read penalty. Every write involves two trips: A write to the cache and a write to the database
  - Missing data.
  - Cache churn.
- By adding a time to live (TTL) value to each write, we are able to enjoy the advantages of each strategy and largely avoid cluttering up the cache with superfluous data.

<p align="center">
  <img alt="alt text" src="elastic1.png" width="400">
  <br>
    <em>Amazon Elastic Cache Index. Source: AWS Official Training</em>
</p>
</n>
</n>
</n>
</n>
<p align="center">
  <img alt="alt text" src="elastic2.png" width="400">
  <br>
    <em>Redis vs Memcached. Source: AWS Official Training</em>
</p>

#### Amazon RDS

- Oracle RAC is not supported by RDS. **important**
- DB2 is supported by RDS (All IBM Websphere products are supported by AWS) 
- An Oracle Real Application Clusters (RAC) One Node option provides virtualized servers on a single machine. 
- There is no automatic way to promote the read replica on the backup region as the master database, and when you do,  when you do, the RDS instance will reboot. 
- You can promote the read replica directly to a standalone DB instance. It is not necessary to make a snapshot and recreate the cluster
- MySQL does not support auto scaling for read replicas.

##### Amazon RDS storage types

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

##### Troubleshooting Scenario

**Scenario**: Amazon CloudWatch DiskQueueDepth metric for the DB instance increases suddenly during peak usage periods.
**Solution**: Double the amount of I/O that DB instance can handle

#### AWS DynamoDB

- Fully-managed NoSQL database service that makes it simple and cost effective to store and retrieve any amount of data
DynamoDB helps offload the administrative burden of operating and scaling a highly-available distributed database cluster.
- This storage alternative meets the latency and throughput requirements of highly demanding applications by providing single-digit millisecond latency.
- DynamoDB stores structured data in tables, indexed by primary key, and allows low-latency read and write access to items ranging from 1 byte up to 400 KB.

<p align="center">
  <img alt="alt text" src="dynamo3.png" width="400">
  <br>
    <em>Dynamo Global Secondary Index vs Local Secondary Index. Source: AWS Official Training</em>
</p>

##### DynamoDB Accelerator

- DynamoDB Accelerator is used for caching requests if you need response times in microseconds. This is very expensive.
  

##### Global Tables:

  - Provide you with a fully managed, multi-region, and multi-master database that provides fast, local, read and write performance for massively scaled, global applications.
  - Replicates your Amazon DynamoDB tables automatically across your choice of AWS regions.
  - Searching for archives in Glacier takes a long time, then it is advisable to store the search criteria and archive ID to a database for faster search.
  - You can purchase reserved capacity in advance to lower the costs of running your DynamoDB instance.
  - With reserved capacity, you pay a one-time upfront fee and commit to a minimum usage level over a period of time significant cost savings compared to on-demand provisioned throughput settings.
- You can only set the auto scaling target utilization values between 20 and 90 percent for your read and write capacity, not 100%.

<p align="center">
  <img alt="alt text" src="dynamo1.png" width="400">
  <br>
    <em>Dynamo DB Global Tables. Source: AWS Official Training</em>
</p>

##### DynamoDB conditional writes

- According to the log, the problem is that a second read gets the value from the table before a first read updates it. You can use conditional writes to prevent this issue.


<p align="center">
  <img alt="alt text" src="dynamo2.png" width="400">
  <br>
    <em>Dynamo DB Caching. Source: AWS Official Training</em>
</p>

#### Amazon Redshift

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


### Developer_tools

#### AWS_CodeDeploy

- CodeDeploy can also deploy a serverless Lambda function. 
- You do not need to make changes to your existing code before you can use CodeDeploy.

### End_user_Computing

#### AppStream2_0

- Fully managed application streaming service. 
- You centrally manage your desktop applications on AppStream 2.0 and securely deliver them to any computer.
- Easily scale to any number of users across the globe without acquiring, provisioning, and operating hardware or infrastructure.

#### AWS_WorkSpaces

- Enables you to provision virtual, cloud-based Microsoft Windows or Amazon Linux desktops for your users, known as WorkSpaces
- Eliminates the need to procure and deploy hardware or install complex software
- Amazon WorkSpaces Application Manager (Amazon WAM) offers a fast, flexible, and secure way for you to deploy and manage applications for Amazon WorkSpaces with Windows.
- Amazon WAM accelerates software deployment, updates, patching, and retirement by packaging Microsoft Windows desktop 


### Machine_Learning

#### Amazon Lex

- Let you create a chatbot to use as Interactive Voice Response (IVR).
- Building conversational interfaces into any application using voice and text.
- Provides the advanced deep learning functionalities of automatic speech recognition (ASR) 

#### Amazon Comprehend

- Takes the transcription of recordings, and applies speech analytics machine learning to the call to identify sentiment, keywords, adherence to company policies, and more.

#### Amazon Polly

Provides text-to-speech in all contact flows.

#### Amazon Transcribe

Grabs conversation recordings from Amazon S3, and transcribes them to text so you can review the audio.

### Management_Goverment

# The AWS Service Catalog 

- Primarily used to allow organizations to create and manage catalogs of IT services that are approved for use on AWS. - It enables you to centrally manage commonly deployed IT services and helps you achieve consistent governance and meet your compliance requirements while enabling users to quickly deploy only the approved IT services they need. 
- This service is not suitable for migrating your virtual machines.


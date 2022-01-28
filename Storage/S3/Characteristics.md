# Simple Service Storage - S3

Amazon S3 is a fully managed object based storage that is high available, highly durable, very cost effective, and widely accessible. 

- Objects stored in S3 have a durability of 11 nines (99.999999999%).
- The availability of S3 data objects is currently four nines (99.99%). 
- When looking at availability AWS ensure that the up time of Amazon S3 is 99.99% to enable you to access your stored data. The durability percentage refers to the probability of maintaining your data without it being lost through corruption, degradation of data, or other unknown potential damaging effects. When uploading objects to S3, specific objects are used to manage your data.

## storage classes

- Standard
  - The Standard Storage class is now more cost effective and offers greater durability.
- Standard Infrequent Access
  - Standard-IA
    - Charge an additional cost to retrieve and access the data.
    - Require very little need to be accessed.
  - One Zone-IA
    - Requires very little need to be accessed.
    - Does not replicate its data across multiple availability zones, and so only offers a 99.5% availability SLA
- Intelligent Tiering
  - great for unpredictable access patterns.
  - Will move data between two tiers, a frequently accessed tier and a more cost effective infrequent accessed tier.
  - If data has not been accessed for 30 days or more then Intelligent Tiering will move data into the Infrequent Accessed tier.
  - The next time this object is accessed, it will be moved back into the Frequently Accessed tier and the 30-day timer will be reset.
  - no retrieval costs for your data like there is with Standard-IA and One Zone-IA. 
  - A small monthly cost associated to each object that is monitored 
  - Each object must be larger than 128 kilobytes. 
- Reduced Redundancy (no longer recommended by AWS)

## Security

- Bucket Policies
  - Access Controls within specific JSON.
  - JSON policies
  - Controls access to data in associated bucket.
  - Policy conditions can make conditions very specific.
  - Added granularity to buckets access.

- Access Control Lists
  - Control access for users outside own AWS account, such us public access.
  - Not as granular as bucket policies.
  - Permissions can be broad in access, e.g list objects or write objects.

- Data Encryption
  - Server-side and client-side encryptions.
  - SSE-S3
  - SSE-KMS
  - SSE-C
  - CSE-C
  - SSL is supported.

## Data Management

- Versioning
  - Allow multiple versions of the same object to exist.
  - Recover accidental deletion or malicious activity.
  - Not enabled by default
  - Once enabled, cannot be disabled, only suspended.

- Lifecycle rules
  - Automatic method of managing lifecycle of data.
  - Specific criteria to move automatically move data between storage classes.


## Use cases

- Data backup
- Statick content & websites
- Large Data Sets
  - Computational
  - Scientific
  - Mathematical
- Service Integration
  - EBS: snapshot backup stored in S3
  - AWS CloudTrail: Log files are sent to pre-configured S3 buckets
  - Amazon Cloudfront: Cloudfront origin within a distribution

## Pricing
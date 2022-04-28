# AWS Route53

- For EC2 instances, always use a Type A Record without an Alias. For ELB, Cloudfront and S3, always use a Type A Record with an Alias and finally, for RDS, always use the CNAME Record with no Alias.
- Allows you to enable Domain Name System Security Extensions (DNSSEC) signing for all existing and new public hosted zones, and enable DNSSEC validation
- Provides data origin authentication and data integrity verification for DNS
- Can associate a VPC from one account with a private hosted zone in a different account:
  - First must authorize the association.
  - You can’t use the AWS console either to authorize the association or associate the VPCs with the hosted zone.
- AWS CLI – using the create-vpc-association-authorization in the AWS CLI (Authorize the association of the VPC with the private hosted zone)
- You must submit one authorization request for each VPC.
- When you authorize the association, you must specify the hosted zone ID, so the private hosted zone must already exist.
- You can’t use the Route 53 console either to authorize the association of a VPC with a private hosted zone or to make the association.
- Route 53 will not route directly to an S3 bucket. You could configure the S3 bucket to be a static website, but you would be unable to receive the file. 
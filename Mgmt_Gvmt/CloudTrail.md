# AWS CloudTrail

- AWS service that helps you enable governance, compliance, and operational and risk auditing of your AWS account.
- Actions taken by a user, role, or an AWS service are recorded as events in CloudTrail.
- Events include actions taken in the AWS Management Console, AWS Command Line Interface, and AWS SDKs and APIs.
- You can also enable the tracking of multi-region and global events.
- Log files delivered by CloudTrail to your bucket are encrypted by Amazon server-side encryption with Amazon S3-managed encryption keys (SSE-S3)
- Extra-secure and directly manageable, you can instead use server-side encryption with AWS KMS–managed keys (SSE-KMS) for your CloudTrail log files.
- You can enable CloudTrail log file integrity Validation to verify logs in case of tampering.

## Organization trail

- Organization trails log events for the management account and all member accounts in the organization.
- To create an organization trail, ensure that the “Enable for all accounts in my organization” option is checked when you create a new CloudTrail trail.
- Choose whether to create an organization trail in all regions or a single region
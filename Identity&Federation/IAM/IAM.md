# IAM

IAM general information, tips &amp; tricks and Reference URLs. For other topics on AWS, you can refer to [this link](https://mgonzalezo.com).

- [IAM](#iam)
  - [General_Details](#general_details)
  - [IAM Policies](#iam-policies)
  - [Take-away information](#take-away-information)
  - [IAM AWS Managed Policies](#iam-aws-managed-policies)
  - [IAM Policies Conditions](#iam-policies-conditions)
  - [IAM Policies Variables and Tags](#iam-policies-variables-and-tags)
  - [IAM Roles vs Resource Based Policies](#iam-roles-vs-resource-based-policies)

## General_Details

- Users: long term credentials
- Groups
- Roles: short-term credentials, use STS

  - EC2 Instance roles: uses EC2 metadata service. One role at a time per instance.
  - Service roles: API gateway, CodeDeploy
  - Cross Account Roles, avoid sharing users' credentials

- Policies:

  - AWS managed: Defined by AWS changing over time to do sth speceific
  - Customer managed: Customer creating policies, can evolve
  - Inline Policies: Policies assigned to one specific user or role, cannot be shared accross users or roles.
  - Resource Based Policies (S3 buckets)

## IAM Policies

1. Anatomy:
    - version
    - Statement
        - Effect
        - Action
        - Resource
        - Condition
        - Effect
        - Action
        - Resource
        - Condition

## Take-away information

- To improve security, always use the least privilege
  - Access Advisor: See granted permissions and when last accessed.
  - Access Analyzer: Analyze AWS resources that are shared with external entities.
- Explicit **Deny** always has precendence over **Allow**.

## IAM AWS Managed Policies

- NoAction: In case you don't want to deny all actions, but just some specific actions

## IAM Policies Conditions

- Operators
  - String (StringEquals, StringNoEquals, StringLike)
  - Numeric(NumericEquals, NumericNoEquals, NumericLessThan)
  - Date (DateEquals, DateNoEquals, DateLessThan)
  - Boolean
  - (Not) IP address
  - ArnEquals, ArnLike
  - Null: Condition

## IAM Policies Variables and Tags

- AWS Specific
  - aws:TokenIssueTime, aws:userid
- Service Specific
  - s3:prefix, s3:max-keys
- Tag Based
  - iam:ResourceTag/key-name

## IAM Roles vs Resource Based Policies

- Attach a policy to a resource (S3 bucket policy) or using role as proxy.
  - Using role as proxy: user gives up original permissions.
  - Attach a policy: the principal doesn't have to give up any permissions.
  - 
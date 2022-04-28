## IAM


- [IAM](#iam)
- [General_Details](#general_details)
- [IAM Policies](#iam-policies)
- [Take-away information](#take-away-information)
- [IAM AWS Managed Policies](#iam-aws-managed-policies)
- [IAM Policies Conditions](#iam-policies-conditions)
- [IAM Policies Variables and Tags](#iam-policies-variables-and-tags)
- [IAM Roles vs Resource Based Policies](#iam-roles-vs-resource-based-policies)
- [Other details](#other-details)

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

## Other details

- Grant cross-account access to your resources:
- The resource that you want to share must support resource-based policies.
- Unlike a user-based policy, a resource-based policy specifies who (in the form of a list of AWS account ID numbers) can access that resource.
- resource-based policy: User still works in the trusted account and does not have to give up his or her user permissions 
- Service role:
  - AWS Identity and Access Management (IAM) that grants permissions to an AWS service so that the service can access AWS resources
  - Systems Manager scenarios require a service role. When you create a service role for Systems Manager, you choose the permissions to grant in order for it to access or interact with other AWS resources
- Service-linked role:
  - Predefined by Systems Manager and includes all the permissions that the service requires to call other AWS services on your behalf.
- The use of "AssumeRoleWithWebIdentity" is wrong which is only for Web Identity Federation (Facebook, Google, and other social logins). 

- An IAM role is an IAM identity that you can create in your account that has specific permissions.
- An IAM role is similar to an IAM user, in that it is an AWS identity with permission policies that determine what the identity can and cannot do in AWS. However, instead of being uniquely associated with one person, a role is intended to be assumable by anyone who needs it

- A role does not have standard long-term credentials such as a password or access keys associated with it. Instead, when you assume a role, it provides you with temporary security credentials for your role session.
- To delegate permission to access a resource, you create an IAM role in the trusting account that has two policies attached:
  - The permissions policy grants the user of the role the needed permissions to carry out the intended tasks on the resource.
  - The trust policy specifies which trusted account members are allowed to assume the role.


<p align="center">
  <img alt="alt text" src="iam1.png" width="400">
  <br>
    <em>Service Role Flow. Source: https://portal.tutorialsdojo.com/</em>
</p>
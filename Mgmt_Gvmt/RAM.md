# AWS RAM

- Enables you to share specified AWS resources that you own with other AWS accounts. 
- How to enable:
  - From the AWS RAM CLI, use the enable-sharing-with-aws-organizations command.
  - Name of the IAM service-linked role that can be created in accounts when trusted access is enabled: AWSResourceAccessManagerServiceRolePolicy.
- Trusted access
  - Enable an AWS service that you specify, called the trusted service, to perform tasks in your organization and its accounts on your behalf.****
  - Granting permissions to the trusted service but does not otherwise affect the permissions for IAM users or roles.
  - When you enable access, the trusted service can create an IAM role called a service-linked role in every account in your organization. 
  - That role has a permissions policy that allows the trusted service to do the tasks that are described in that service’s documentation.
  - Enables you to specify settings and configuration details that you would like the trusted service to maintain in your organization’s accounts on your behalf.
- Trust policy of a service-linked role cannot be modified.
- Only the linked AWS service can assume a service-linked role, which is why you cannot modify the trust policy of a service-linked role.
- SCPs DO NOT affect any service-linked role. Service-linked roles enable other AWS services to integrate with AWS Organizations and can’t be restricted by SCPs.
Sample question: "simple and effective solution that would allow the service to perform its tasks on the organization accounts on the moderator’s behalf"
- "service-linked role" This is required by some services that must access resources in another service, such as an Amazon S3 bucket.
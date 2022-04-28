# Amazon SCP:

- SCPs are available only in an organization that has all features enabled. 
- SCPs aren't available if your organization has enabled only the consolidated billing features.
- An SCP defines a guardrail, or sets limits, on the actions that the account's administrator can delegate to the IAM users and roles in the affected accounts.
- Determines what services and actions can be delegated by administrators to the users and roles
- Does not grant any permissions. Instead, SCPs are JSON policies that specify the maximum permissions for an organization or organizational unit (OU).
- You cannot directly assign an IAM policy to an OU.
- SCPs do affect the root user along with all IAM users and standard IAM roles in any affected account
- By default, an SCP named FullAWSAccess is attached to every root, OU, and account. This default SCP allows all actions and all services.
- If you want the master account to have full administrative control over an invited member account, 
you must create the  OrganizationAccountAccessRole IAM role in the member account and grant permission to the master account to assume the role.
- An SCP cannot be overridden, even when users within the account have administrative rights.
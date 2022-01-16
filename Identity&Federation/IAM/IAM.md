# IAM

IAM general information, tips &amp; tricks and Reference URLs. For CKAD Tips, you can refer to [this link](https://mgonzalezo.com).

Users: long term credentials
Groups
Roles: short-term credentials, use STS

- EC2 Instance roles: uses EC2 metadata service. One role at a time per instance.
- Service roles: API gateway, CodeDeploy
- Cross Account Roles, avoid sharing users' credentials

Policies:

- AWS managed: Defined by AWS changing over time to do sth speceific
- Customer managed: Customer creating policies, can evolve
- Inline Policies: Policies assigned to one specific user or role, cannot be shared accross users or roles.

Resource Based Policies (S3 buckets)

IAM Policies:

1. Anatomy:
    - version
    - Statement
        - [x] Effect
        - [x] Action
        - [x]Resource
        - [x]Condition
        - [x]Effect
        - [x]Action
        - [x]Resource
        - [x]Condition

# AWS Systems Manager Parameter Store

Provides secure, hierarchical storage for configuration data management and secrets management.
You can store data such as passwords, database strings, and license codes as parameter values
You can store values as plain text or encrypted data
You can reference Systems Manager parameters in your scripts, commands, SSM documents, and configuration and automation workflows
benefits:
	You can use a secure, scalable, hosted secrets management service with no servers to manage.
    Improve your security posture by separating your data from your code.
    Store configuration data and encrypted strings in hierarchies and track versions.
    Control and audit access at granular levels.


## Key Question

**AWS Systems Manager Parameter Store vs Secrets Manager? when to use each of them?**
**Answer** If you want a single store for configuration and secrets, you can use Parameter Store. If you want a dedicated secrets store with lifecycle management, use Secrets Manager.
# AWS CloudFormation:


- The cfn-init helper script reads template metadata from the AWS::CloudFormation::Init key and acts accordingly to:
  - Fetch and parse metadata from CloudFormation
  - Install packages
  - Write files to disk
  - Enable/disable and start/stop services

Source: From <https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/cfn-init.html> 


- The cfn-hup helper is a daemon that detects changes in resource metadata and runs user-specified actions when a change is detected. This allows you to make configuration updates on your running Amazon EC2 instances through the UpdateStack API action.

Source: From <https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/cfn-hup.html> 

- Using roles to grant permissions to applications that run on EC2 instances requires a bit of extra configuration. 
- An application running on an EC2 instance is abstracted from AWS by the virtualized operating system. Because of this extra separation, an additional step is needed to assign an AWS role and its associated permissions to an EC2 instance and make them available to its applications. This extra step is the creation of an instance profile that is attached to the instance.

- The instance profile contains the role and can provide the role’s temporary credentials to an application that runs on the instance. 
- Those temporary credentials can then be used in the application’s API calls to access resources and to limit access to only those resources that the role specifies. Note that only one role can be assigned to an EC2 instance at a time, and all applications on the instance share the same role and permissions.

Source: From <https://portal.tutorialsdojo.com


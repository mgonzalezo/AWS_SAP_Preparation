# AWS ECS

You can register Spot Instances to your Amazon ECS clusters.
Amazon EC2 terminates, stops, or hibernates your Spot Instance when the Spot price exceeds the maximum price for your request or capacity is no longer available
Amazon EC2 provides a Spot Instance interruption notice, which gives the instance a two-minute warning before it is interrupted.
ECS Spot Instance draining is enabled on the instance, ECS receives the Spot Instance interruption notice and places the instance in DRAINING status.
Container instance is set to DRAINING -> Amazon ECS prevents new tasks from being scheduled for placement on the container instance
Spot Instance draining is disabled by default and must be manually enabled by adding the line:
ECS_ENABLE_SPOT_INSTANCE_DRAINING=true on your /etc/ecs/ecs.config file.
The recommended best practice is to select the “Diversified” strategy, to maximize provisioning choices, while reducing the costs. 

Task definitions
-Split into separate parts: the task family, the IAM task role, the network mode, container definitions, volumes, 
  task placement constraints, and launch types.
The networking behavior of Amazon ECS tasks hosted on Amazon EC2 instances is dependent on the network mode defined in the task definition. The following are the available network modes. Amazon ECS recommends using the awsvpc network mode unless you have a specific need to use a different network mode.
-**awsvpc**: The task is allocated its own elastic network interface (ENI) and a primary private IPv4 address. This gives the task the same networking properties as Amazon EC2 instances.
-**bridge**: The task utilizes Docker's built-in virtual network which runs inside each Amazon EC2 instance hosting the task.
-**host**: The task bypasses Docker's built-in virtual network and maps container ports directly to the ENI of the Amazon EC2 instance hosting the task. As a result, you can't run multiple instantiations of the same task on a single Amazon EC2 instance when port mappings are used.
-**none**: The task has no external network connectivity.

# VPC

- Internet access from a private subnet requires network address translation (NAT).
- 

## Lambda on VPC

You can configure a Lambda function to connect to private subnets in a virtual private cloud (VPC) in your AWS account.

- Use Amazon Virtual Private Cloud (Amazon VPC) to create a private network for resources such as databases, cache instances, or internal services.
- Connect your function to the VPC to access private resources while the function is running.
- When you connect a function to a VPC, Lambda assigns your function to a Hyperplane ENI (elastic network interface) for each subnet in your function’s VPC configuration.
- Lambda creates a Hyperplane ENI the first time a unique subnet and security group combination is defined for a VPC-enabled function in an account.
- To give internet access to an Amazon VPC-connected Lambda function, route its outbound traffic to a NAT gateway or NAT instance in a public subnet.
- Lambda functions do not, and cannot, have public IP addresses. You cannot send traffic to the internet, which happens via the VPC’s Internet Gateway, unless you have a public IP.
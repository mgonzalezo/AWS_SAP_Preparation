# ELB

## Application Load Balancer:

- You can host multiple TLS secured applications, each with its own TLS certificate.
- In order to use SNI, all you need to do is bind multiple certificates to the same secure listener on your load balancer.
- ALB will automatically choose the optimal TLS certificate for each client. These features are provided at no additional charge.
- A wildcard certificate can only handle multiple sub-domains but not different domain names.
- SNI Custom SSL
  - Provides an efficient way to deliver content over HTTPS using your own domain and SSL certificate
  - Relies on the SNI extension of the Transport Layer Security protocol
  - Allows multiple domains to serve SSL traffic over the same IP address by including the hostname which the viewers are trying to connect to.
- ELB access logs will be delayed by at least 5 minutes before they arrive in Amazon S3

- In the ALB, you can create a listener that uses encrypted connections (also known as SSL offload). This feature enables traffic encryption between your load balancer and the clients that initiate SSL or TLS sessions.
- To use an HTTPS listener, you must deploy an SSL/TLS server certificate on your load balancer. The load balancer uses this certificate to terminate the connection and then decrypt requests from clients before sending them to the targets.
- Although you can terminate the SSL in the EC2 instance, this setup is not recommended in this scenario. It is best to store the SSL certificate in IAM or in AWS Certificate Manager (ACM) where you can control which teams, either the Security or the Development team, can have access.
- The clients access the website through the Load Balancer and not the EC2 instances directly. Using CloudHSM to store your SSL certificate will just increase your costs without satisfying the requirement.
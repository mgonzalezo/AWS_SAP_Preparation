# Amazon EKS (Elastic Kubernetes Service)

- Managed Kubernetes service for running Kubernetes on AWS without managing control plane.
- Automatically manages availability and scalability of Kubernetes control plane nodes.
- Integrates with AWS services: ELB, IAM, VPC, CloudWatch.
- Supports standard Kubernetes tooling and plugins.

## Amazon EKS Auto Mode (2025)

Fully automated infrastructure management for EKS clusters.

### Key Features

- Automated compute management with intelligent node provisioning.
- Automatic scaling and lifecycle management.
- No manual node group configuration required.
- AWS handles complete Kubernetes cluster infrastructure lifecycle.

### Recent Enhancements (2025)

#### AWS Local Zones Support
- Deploy EKS Auto Mode nodes to AWS Local Zones.
- Run applications closer to end users for ultra-low latency.

#### Separate Pod Subnets
- Support for separate pod subnets in the NodeClass.
- Optional keys: `podSubnetSelectorTerms` and `podSecurityGroupSelectorTerms`.
- Better network isolation and security control.

#### Capacity Reservations Control
- Control deployment of workloads into EC2 On-Demand Capacity Reservations (ODCRs).
- Use `capacityReservationSelectorTerms` key in NodeClass.
- Optimize costs with capacity reservation utilization.

#### Network Proxy Support
- Forward network proxy support in the NodeClass.
- Configure through `advancedNetworking` key.
- Required for environments with restricted internet access.

#### GovCloud Availability
- EKS Auto Mode now available in AWS GovCloud (US-East) and (US-West).
- Meets compliance requirements for government workloads.

### Benefits

- Reduces operational overhead significantly.
- Eliminates manual capacity planning.
- Optimizes costs through intelligent resource allocation.
- Faster cluster setup and management.

## Amazon EKS Hybrid Nodes (2025)

Use on-premises and edge infrastructure as nodes in Amazon EKS clusters.

### Architecture

- AWS manages the Kubernetes control plane (hosted in AWS).
- You manage hybrid nodes in your on-premises or edge environments.
- Single EKS cluster spans cloud and on-premises infrastructure.

### Supported Deployment Models

- **Hybrid-only clusters**: All nodes on-premises or at edge.
- **Mixed clusters**: Combine nodes in AWS Regions, Local Zones, Outposts, and on-premises.
- **Burst-to-cloud**: Add cloud capacity to on-premises clusters during peak demand.
- **Add on-premises capacity**: Extend cloud clusters with on-premises resources.

### Supported Features

- Amazon EKS add-ons (VPC CNI, CoreDNS, kube-proxy).
- Amazon EKS Pod Identity for pod-level IAM credentials.
- Cluster access entries for authentication and authorization.
- Cluster insights for monitoring and troubleshooting.
- Extended Kubernetes version support.

### Use Cases

- **Hybrid cloud**: Workloads that must run on-premises but need cloud integration.
- **Edge computing**: Process data at edge locations with centralized control plane.
- **Data residency**: Keep data on-premises while using AWS-managed control plane.
- **Migration**: Gradual migration from on-premises to cloud.
- **Burst capacity**: Scale to cloud during peak demand periods.

### Pricing

- Pay-per-hour for vCPU resources when hybrid nodes are attached to EKS clusters.
- No additional charge for EKS control plane (standard EKS pricing).
- Separate charges for AWS resources (if bursting to cloud).

## EKS Standard Features

### Cluster Management

- Automated Kubernetes version upgrades.
- Automated patching of control plane.
- Multi-AZ control plane for high availability.
- Integration with AWS CloudTrail for audit logs.

### Compute Options

- **Managed Node Groups**: AWS-managed EC2 instances with automated updates.
- **Self-Managed Nodes**: Full control over EC2 instances.
- **AWS Fargate**: Serverless compute for pods (no node management).
- **Hybrid Nodes (2025)**: On-premises and edge nodes.

### Networking

- VPC native networking with AWS VPC CNI.
- Support for custom CNI plugins (Calico, Cilium, Weave Net).
- Network policies for pod-to-pod communication control.
- Integration with AWS Load Balancers (ALB, NLB).
- PrivateLink support for private API server access.

### Security

- IAM for cluster authentication and RBAC authorization.
- EKS Pod Identity for pod-level IAM credentials (2025).
- Secrets encryption with AWS KMS.
- Security groups for pods.
- Integration with AWS Security Hub.
- Compliance: PCI DSS, HIPAA, SOC, ISO.

### Observability

- CloudWatch Container Insights for metrics and logs.
- CloudWatch Logs integration.
- AWS X-Ray for distributed tracing.
- Prometheus metrics support.
- Fluent Bit and Fluentd for log forwarding.

### Add-ons

- **VPC CNI**: Networking plugin for AWS VPC integration.
- **CoreDNS**: DNS service for Kubernetes clusters.
- **kube-proxy**: Network proxy for Kubernetes services.
- **EBS CSI Driver**: Amazon EBS volumes for persistent storage.
- **EFS CSI Driver**: Amazon EFS for shared file storage.
- **AWS Load Balancer Controller**: Manage ALB and NLB from Kubernetes.
- **Amazon GuardDuty**: Threat detection for EKS clusters.

## EKS Fargate

- Serverless compute engine for Amazon EKS.
- No nodes to manage - AWS runs containers directly.
- Pay only for vCPU and memory consumed by pods.
- Automatic scaling based on pod requirements.
- Each pod runs in isolated compute environment.

### Fargate Profiles

- Define which pods run on Fargate based on namespaces and labels.
- Multiple Fargate profiles per cluster.
- Mix Fargate and EC2 nodes in same cluster.

## EKS on AWS Outposts

- Run EKS clusters on AWS Outposts for on-premises deployment.
- Local control plane option for disconnected operation.
- Same EKS APIs and tooling as cloud.

## Best Practices

- Use EKS Auto Mode (2025) for simplified infrastructure management.
- Enable control plane logging for audit and troubleshooting.
- Use Managed Node Groups or Auto Mode for easier node management.
- Implement Pod Security Standards for workload security.
- Use IAM Roles for Service Accounts (IRSA) or EKS Pod Identity (2025).
- Enable cluster autoscaling for dynamic workload scaling.
- Use separate subnets for control plane and data plane.
- Regular ly update to latest Kubernetes version.

## Exam Tips

- EKS manages Kubernetes control plane - you manage worker nodes (or use Auto Mode/Fargate).
- EKS Auto Mode (2025) fully automates infrastructure management.
- EKS Hybrid Nodes (2025) allow on-premises and edge nodes in EKS clusters.
- Fargate provides serverless compute - no node management required.
- EKS Pod Identity (2025) simplifies pod-level IAM credentials.
- Hybrid Nodes support burst-to-cloud and mixed deployment scenarios.
- EKS integrates with AWS services: ALB, NLB, EBS, EFS, CloudWatch, IAM.
- Use Managed Node Groups for automated EC2 node management.
- EKS control plane is multi-AZ by default for high availability.
- Support for standard Kubernetes tooling (kubectl, Helm, etc.).

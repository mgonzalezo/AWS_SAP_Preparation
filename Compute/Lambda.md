# AWS Lambda

- Serverless compute service that runs code in response to events.
- No server management - AWS handles infrastructure provisioning and scaling.
- Pay only for compute time consumed (per millisecond billing).
- Automatic scaling from a few requests per day to thousands per second.

## Key Features

- Supports multiple runtimes: Python, Node.js, Java, .NET, Go, Ruby, custom runtimes.
- Maximum execution time: 15 minutes (standard functions).
- Memory allocation: 128 MB to 10,240 MB (10 GB).
- Ephemeral storage: Up to 10 GB in /tmp directory.
- Concurrent executions: 1,000 default (can request increase).

## Lambda Durable Functions (2025)

New capability announced December 2025 for building reliable multi-step applications and AI workflows.

### Key Capabilities

- **Long-running workflows**: Execute for up to 366 days (1 year) through checkpoint-and-replay.
- **Automatic checkpointing**: Progress automatically saved without custom state management.
- **Automatic recovery**: Resumes from last checkpoint after failures.
- **No additional infrastructure**: Built into Lambda - no Step Functions or external orchestration needed.

### How It Works

- Uses checkpoint and replay mechanism known as durable execution.
- Add open source durable execution SDK to function code.
- Use SDK primitives:
  - **Steps**: Add automatic checkpointing and retries to business logic.
  - **Waits**: Suspend execution efficiently without compute charges during waiting periods.

### Supported Runtimes (2025)

- Python 3.13 and 3.14
- Node.js 22 and 24

### Availability (2025)

Available in 15 AWS Regions including:
- US East (Ohio, N. Virginia)
- US West (Oregon)
- Europe (Ireland, Frankfurt, Milan, Stockholm, Spain)
- Asia Pacific (Sydney, Hong Kong, Tokyo, Singapore, Mumbai, Malaysia, Thailand)

### Use Cases

- **Order processing**: Multi-step workflows with external system integration.
- **User onboarding**: Complex sequences with waiting periods and approvals.
- **AI-assisted workflows**: Long-running AI agent tasks with multiple steps.
- **Batch processing**: Jobs that require hours or days to complete.
- **Human-in-the-loop workflows**: Wait for manual approvals without maintaining connections.

### Differences from Standard Lambda

| Feature | Standard Lambda | Durable Functions |
|---------|----------------|-------------------|
| Max duration | 15 minutes | 366 days |
| State management | Manual (DynamoDB, etc.) | Automatic checkpointing |
| Failure recovery | Custom retry logic | Automatic from checkpoints |
| Long waits | External orchestration needed | Built-in wait primitive |

## Lambda@Edge

- Run Lambda functions at CloudFront edge locations.
- Customize content delivery with minimal latency.
- Execute functions closer to end users.
- Use cases: URL rewriting, A/B testing, authentication, content generation.

## VPC Integration

- Connect Lambda functions to VPC to access private resources.
- Access RDS databases, ElastiCache, internal services.
- Lambda assigns Hyperplane ENI for VPC connectivity.
- To access internet from VPC Lambda: route through NAT Gateway in public subnet.
- Lambda functions do not have public IP addresses.

## Event Sources

- **Synchronous invocation**: API Gateway, Application Load Balancer, SDK calls.
- **Asynchronous invocation**: S3, SNS, EventBridge, SES.
- **Stream-based**: Kinesis Data Streams, DynamoDB Streams, SQS.
- **Poll-based**: SQS, Kafka, Amazon MQ.

## Layers

- Share code, libraries, and dependencies across multiple functions.
- Reduce deployment package size.
- Separate business logic from dependencies.
- Maximum 5 layers per function.
- Total unzipped size (function + layers) cannot exceed 250 MB.

## Environment Variables

- Store configuration separately from code.
- Can be encrypted with KMS.
- Maximum 4 KB total size for all environment variables.

## Concurrency Controls

- **Reserved concurrency**: Guarantee capacity for critical functions.
- **Provisioned concurrency**: Pre-initialize execution environments for consistent low latency.
- Prevents cold starts for latency-sensitive applications.

## Destinations

- Configure success and failure destinations for asynchronous invocations.
- Send results to SNS, SQS, EventBridge, or another Lambda function.
- Better than DLQ - includes full invocation record.

## Performance Optimization

- Increase memory to get proportionally more CPU and network bandwidth.
- Use provisioned concurrency to eliminate cold starts.
- Minimize deployment package size for faster cold starts.
- Reuse connections and SDK clients across invocations (outside handler).
- Use /tmp for caching data between invocations (persists during warm execution environment).

## Security

- Execution role (IAM role) defines permissions Lambda has.
- Resource-based policy defines who can invoke the function.
- VPC integration for network isolation.
- Environment variable encryption with KMS.
- Code signing for deployment integrity.

## Monitoring

- Automatic CloudWatch Logs integration.
- CloudWatch Metrics: invocations, duration, errors, throttles.
- AWS X-Ray for distributed tracing.
- Lambda Insights for enhanced monitoring (CPU, memory, disk, network).

## Pricing

- **Request charges**: Per million requests.
- **Duration charges**: Per GB-second of execution time.
- **Provisioned concurrency**: Hourly charge for pre-warmed capacity.
- **Durable Functions**: No additional cost beyond standard compute charges.
- Free tier: 1 million requests and 400,000 GB-seconds per month.

## Best Practices

- Keep functions single-purpose and stateless.
- Externalize configuration with environment variables or Parameter Store.
- Use layers for shared dependencies.
- Implement idempotency for retry safety.
- Set appropriate timeouts and memory allocations.
- Use provisioned concurrency for latency-critical workloads.
- Monitor and set alarms on error rates and duration.

## Integration with Other AWS Services

- **API Gateway**: Build RESTful and WebSocket APIs.
- **EventBridge**: Event-driven architectures with rules and patterns.
- **Step Functions**: Complex workflow orchestration (alternative to Durable Functions for some use cases).
- **DynamoDB**: Serverless database with stream processing.
- **S3**: Object processing and data transformation.
- **SNS/SQS**: Message processing and asynchronous workflows.

## Exam Tips

- Lambda has 15-minute maximum execution time for standard functions.
- Lambda Durable Functions (2025) can run up to 366 days with automatic checkpointing.
- VPC Lambda functions need NAT Gateway for internet access (no public IP).
- Increase memory allocation to get more CPU and network bandwidth.
- Provisioned concurrency eliminates cold starts (pre-warmed execution environments).
- Use Lambda Layers to share code across functions (max 5 layers).
- Asynchronous invocations can use Destinations for success/failure routing.
- Lambda@Edge runs functions at CloudFront edge locations for low latency.
- Durable Functions eliminate need for Step Functions for many multi-step workflows.
- Maximum deployment package size: 50 MB (zipped), 250 MB (unzipped including layers).

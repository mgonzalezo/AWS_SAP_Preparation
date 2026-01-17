# Amazon Bedrock

- Fully managed service offering high-performing foundation models (FMs) from leading AI companies through a single API.
- No infrastructure management required - serverless architecture.
- Access to models from AI21 Labs, Anthropic, Cohere, Meta, Mistral AI, Stability AI, and Amazon.
- Build generative AI applications with security, privacy, and responsible AI controls.

## Foundation Models

- Multiple model choices for different use cases and price points.
- Models support text, image, and video generation.
- Pay-as-you-go pricing with no minimum commitments.
- Your data is not used to improve base models - complete privacy.

## Amazon Nova Models (2025)

Amazon Nova is AWS's new generation of foundation models delivering frontier intelligence and industry-leading price performance.

### Text Understanding Models

- **Amazon Nova Micro**: Text-only model with lowest latency responses at very low cost. Best for simple tasks like classification and summarization.
- **Amazon Nova Lite**: Very low-cost multimodal model for processing image, video, and text inputs. Lightning-fast performance.
- **Amazon Nova Pro**: Highly capable multimodal model with best combination of accuracy, speed, and cost for wide range of tasks.
- **Amazon Nova Premier**: Most capable model for complex reasoning and enterprise applications requiring highest accuracy.

### Content Generation Models

- **Amazon Nova Canvas**: State-of-the-art image generation model for studio-quality images.
- **Amazon Nova Reel**: State-of-the-art video generation model for creating short video clips from text prompts.

### Amazon Nova Act (2025)

- Agentic AI service for automating browser-based tasks.
- Over 90% reliability for enterprise deployments.
- Can navigate websites, fill forms, and extract data automatically.
- Powered by custom Nova 2 Lite model.

## Knowledge Bases

- Retrieval Augmented Generation (RAG) capability without custom code.
- Connect foundation models to your company data sources.
- **Multimodal retrieval (2025)**: Ingest and retrieve text, images, audio, and video content.
- Support for text or image queries with relevant segments returned.
- Integration with Amazon OpenSearch Service, Amazon Aurora, Pinecone, MongoDB, and Redis Enterprise Cloud.
- Amazon Nova models excel at RAG workloads.
- Use with Amazon S3 Vectors for cost-effective vector storage (up to 90% cost reduction).

## Agents

- Build applications that reason through problems and execute multi-step workflows.
- Automatically break down tasks and create orchestration plans.
- Securely connect to company data through APIs.
- Can invoke AWS Lambda functions and other AWS services.
- Agents handle complex tasks autonomously with minimal human intervention.

## Guardrails

- Implement safeguards for generative AI applications in production.
- Filter undesirable content based on use cases and responsible AI policies.
- Content filters for harmful categories: hate, insults, sexual, violence, misconduct, prompt attacks.
- Denied topics to prevent unwanted subjects from being discussed.
- Word filters to block specific terms and phrases.
- Sensitive information redaction for PII protection (names, addresses, credit cards, SSN, etc.).
- Guardrails are essential for production generative AI applications.

## Model Customization

- **Fine-tuning**: Customize models with labeled training data for specific tasks.
- **Continued pre-training**: Adapt models to specific domains with unlabeled data.
- Private customization ensures your data remains secure.
- Customized models stored in your AWS account.

## Advanced Features

### Batch Inference
- Process large volumes of data asynchronously.
- Up to 50% cost savings compared to on-demand pricing.
- Ideal for non-real-time workloads like document processing.

### Provisioned Throughput
- Purchase model capacity for consistent performance.
- Guaranteed throughput for mission-critical applications.
- Cost savings for high-volume workloads.

### Cross-Region Inference
- Route inference requests across AWS Regions automatically.
- Improved availability and resilience.
- Automatic failover for high availability.

### Web Grounding (2025)
- Models can access current web information for responses.
- Reduces hallucinations by grounding in real-time data.
- Available for Amazon Nova Premier, Nova 2 Pro, and Nova 2 Omni.
- Pricing: $30.00 per 1,000 requests.

## Use Cases

- **RAG applications**: Ground model responses in company-specific data for accuracy.
- **Conversational AI**: Build intelligent chatbots and virtual assistants with context retention.
- **Content generation**: Automated content creation, document generation, image and video creation.
- **Code generation**: Generate, explain, and debug code from natural language.
- **Agent-based automation**: Automate complex multi-step business processes.

## Security and Compliance

- Data encryption at rest and in transit.
- VPC support for network isolation.
- AWS PrivateLink support for private connectivity.
- Integration with AWS IAM for fine-grained access control.
- Compliance certifications: HIPAA eligible, SOC, ISO, PCI DSS.
- Data residency controls for regulatory requirements.

## Integration with AWS Services

- **Amazon S3 Vectors**: Store and query up to 2 billion vectors per index with 100ms latencies.
- **AWS Lambda**: Build serverless generative AI applications.
- **Amazon SageMaker**: Custom model training and deployment.
- **AWS Step Functions**: Orchestrate complex AI workflows.
- **Amazon Kendra**: Enterprise search enhanced with generative AI.

## Exam Tips

- Bedrock is the fully managed service for foundation models - no infrastructure to manage.
- Knowledge Bases provide RAG capability without writing custom integration code.
- Guardrails are required for production applications to filter harmful content and protect sensitive data.
- Amazon Nova models offer best price-performance for AWS workloads.
- Agents automate multi-step tasks with reasoning - different from simple Lambda functions.
- Multimodal retrieval (2025) supports text, image, audio, and video in Knowledge Bases.
- Your data remains private - not used to improve base models.
- Cross-region inference improves availability for mission-critical applications.
- Batch inference saves up to 50% for non-real-time workloads.

# Amazon SageMaker AI

- Fully managed machine learning service to build, train, and deploy ML models at scale.
- Provides tools for every step of the ML lifecycle from data preparation to model deployment.
- Supports traditional ML, deep learning, and generative AI workloads.

## SageMaker Studio

- Integrated development environment (IDE) for machine learning.
- Single web-based interface for all ML development activities.
- Collaborative notebooks with Git integration.
- Visual interface for building, training, and deploying models.

## Generative AI Features (2025)

### Serverless Model Customization (2025)

- Transforms model customization from months-long process to days.
- No infrastructure provisioning or management required.
- AI agent-guided workflow accessible through natural language.
- No deep expertise in reinforcement learning required.

### Supported Customization Techniques

- **Supervised Fine-Tuning (SFT)**: Train models on labeled examples.
- **Direct Preference Optimization (DPO)**: Align models with human preferences.
- **Reinforcement Learning from AI Feedback (RLAIF)**: Use AI feedback to improve models.
- **Reinforcement Learning from Verifiable Rewards (RLVR)**: Train with verifiable reward signals.

### Model Support

- Amazon Nova models (all variants).
- Meta Llama family (Llama 2, Llama 3).
- Qwen models.
- DeepSeek models.
- GPT-OSS models.
- Select models through SageMaker Studio interface.

## Amazon Bedrock Integration (2025)

- Direct access to Amazon Bedrock foundation models inside SageMaker Unified Studio.
- No separate infrastructure provisioning needed.
- Fine-tune and deploy Bedrock models alongside SageMaker workflows.
- Unified experience for all generative AI development.

## SageMaker Data Agent (2025)

- Built-in AI agent in new SageMaker notebooks.
- Understands data context, catalog information, and business metadata.
- Generates intelligent execution plans from natural language descriptions.
- Not just code generation - creates context-aware data workflows.

## Training Capabilities

### Distributed Training

- Automatically distribute training across multiple GPUs and instances.
- Data parallelism and model parallelism strategies.
- Supports large-scale model training (billions of parameters).

### Checkpointless Training (2025)

- Peer-to-peer state recovery mechanism.
- Reduces downtime by 80%+ compared to checkpoint-based recovery.
- Faster recovery from training failures.
- Lower storage costs (no checkpoint storage needed).

### Managed Spot Training

- Use EC2 Spot instances for training to reduce costs by up to 90%.
- Automatic checkpoint and resume on interruption.
- Best for non-time-critical training jobs.

## Model Deployment

### Real-Time Inference

- Low-latency predictions for interactive applications.
- Auto-scaling based on traffic patterns.
- Multi-model endpoints to host multiple models on single endpoint.
- Multi-container endpoints for ensemble models.

### Serverless Inference

- No infrastructure management - automatic scaling.
- Pay only for compute time used during inference.
- Ideal for intermittent or unpredictable traffic.
- Cold start optimization for sub-second response times.

### Batch Transform

- Process large datasets asynchronously.
- Cost-effective for batch predictions.
- No need to maintain persistent endpoints.

### Asynchronous Inference

- Queue requests and process asynchronously.
- Handle large payloads (up to 1 GB).
- Near real-time processing with queueing for spiky traffic.

## Inference Optimization

### EAGLE-Based Adaptive Speculative Decoding (2025)

- Accelerates large language model inference by up to 2.5x.
- Maintains output quality while improving speed.
- Reduces cost per inference by improving throughput.

### Model Optimization

- Model quantization (reduce precision while maintaining accuracy).
- Model compilation with SageMaker Neo.
- Deploy on edge devices, mobile, and IoT.

## MLflow Integration

### Serverless MLflow (2025)

- Create MLflow tracking instances in approximately 2 minutes.
- No server management required.
- MLflow 3.4 support with new tracing capabilities for generative AI.
- Track experiments, models, and deployments.

## SageMaker Feature Store

- Centralized repository for ML features.
- Online store for low-latency access (sub-millisecond).
- Offline store for training and batch inference.
- Feature versioning and lineage tracking.
- Share features across teams and projects.

## SageMaker Pipelines

- Purpose-built CI/CD service for machine learning.
- Automate and orchestrate ML workflows.
- Define multi-step workflows with directed acyclic graphs (DAGs).
- Integration with SageMaker Studio for visual workflow design.

## Model Registry

- Catalog ML models with versioning.
- Track model lineage from data to deployment.
- Model approval workflows for governance.
- Integration with CI/CD pipelines.

## Model Monitoring

- Continuously monitor models in production.
- Detect data drift and model quality degradation.
- Monitor for bias in predictions.
- Automated alerts when issues detected.
- Model explainability with SageMaker Clarify.

## Security and Compliance

- VPC support for network isolation.
- Encryption at rest and in transit.
- IAM integration for access control.
- SageMaker Role Manager for least-privilege permissions.
- Compliance: HIPAA eligible, SOC, ISO, PCI DSS, FedRAMP.

## Cost Optimization

- Savings Plans for predictable workloads (up to 64% savings).
- Managed Spot Training (up to 90% savings).
- Inference recommender to select optimal instance types.
- Automatic model tuning to reduce training costs.

## Use Cases

- **Custom model training**: Train models on proprietary datasets.
- **Generative AI customization**: Fine-tune LLMs for specific domains.
- **MLOps**: Automate ML lifecycle with pipelines and monitoring.
- **Edge deployment**: Deploy models to IoT and mobile devices.
- **Batch predictions**: Process large datasets cost-effectively.

## Exam Tips

- SageMaker provides end-to-end ML platform - from data prep to deployment.
- Serverless options available for both training (2025) and inference.
- Use Managed Spot Training for cost savings (up to 90%) on non-urgent workloads.
- Feature Store centralizes features for reuse across teams.
- SageMaker Pipelines for ML workflow automation (MLOps).
- Model Registry tracks versions and lineage for governance.
- Checkpointless training (2025) reduces recovery time by 80%+.
- EAGLE decoding (2025) accelerates LLM inference by 2.5x.
- Bedrock integration (2025) provides unified generative AI experience.
- SageMaker Data Agent (2025) creates context-aware data workflows from natural language.

# SQS

- Fully managed message queuing service that makes it easy to decouple and scale microservices, distributed systems, and serverless applications.
- To have compatibility with JMS or other protocols like MQTT AMQP, we use Amazon MQ
- You can use SQS to buffer and scale the backend service to accommodate the large incoming traffic. 
- You can save the submitted answers on the SQS Queue and then quickly return the user to a new page stating that the answers are successfully submitted. 
- This is a simple cost-effective design that improves user experience without increasing the capacity of your systems.
- SQS makes it simple and cost-effective to decouple and coordinate the components of a cloud application
you can send, store, and receive messages between software components at any volume, without losing messages or requiring other services to be available all the time
- An SQS queue cannot be used as a direct input for an AWS Step Function workflow.

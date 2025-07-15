# AWS SQS – Use Cases

## 1. Decoupling Microservices
- **Scenario:** Use SQS to decouple producers and consumers in a microservices architecture.
- **Best Practice:** Use message attributes for filtering and dead-letter queues for error handling.

## 2. Buffering and Load Leveling
- **Scenario:** Buffer requests between web servers and backend processing systems to handle traffic spikes.
- **Best Practice:** Use auto-scaling consumers and monitor queue length with CloudWatch.

## 3. Asynchronous Workflows
- **Scenario:** Enable background processing for tasks like image processing, email sending, or report generation.
- **Best Practice:** Use FIFO queues for order-sensitive tasks.

## 4. Distributed Systems Coordination
- **Scenario:** Coordinate tasks across distributed systems (e.g., batch jobs, ETL pipelines).
- **Best Practice:** Use visibility timeouts to prevent duplicate processing.

## 5. Event-Driven Architectures
- **Scenario:** Trigger Lambda functions or other services in response to new messages.
- **Best Practice:** Use SNS to fan out messages to multiple SQS queues.

## Troubleshooting Tips
- Monitor dead-letter queues for failed messages.
- Adjust visibility timeout to match processing time.
- Use CloudWatch metrics for queue depth and age of oldest message.

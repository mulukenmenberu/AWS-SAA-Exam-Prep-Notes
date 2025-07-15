# SQS Cheatsheet (Beginner to Advanced)

## Creating a Queue (Console)
1. Go to the SQS Dashboard in AWS Console
2. Click "Create queue" and choose Standard or FIFO
3. Configure queue settings (name, retention, visibility timeout, encryption, DLQ)
4. Create the queue and note the URL/ARN

## Common CLI Commands
- **List Queues:** `aws sqs list-queues`
- **Create Queue:** `aws sqs create-queue --queue-name MyQueue`
- **Send Message:** `aws sqs send-message --queue-url https://sqs.us-east-1.amazonaws.com/123456789012/MyQueue --message-body "Hello"`
- **Receive Message:** `aws sqs receive-message --queue-url https://sqs.us-east-1.amazonaws.com/123456789012/MyQueue --max-number-of-messages 1`
- **Delete Message:** `aws sqs delete-message --queue-url https://sqs.us-east-1.amazonaws.com/123456789012/MyQueue --receipt-handle <handle>`
- **Purge Queue:** `aws sqs purge-queue --queue-url https://sqs.us-east-1.amazonaws.com/123456789012/MyQueue`
- **Set Queue Attributes:** `aws sqs set-queue-attributes --queue-url ... --attributes VisibilityTimeout=60`

## Important Limits & Defaults
- **Max message size:** 256 KB
- **Max retention period:** 14 days (default 4 days)
- **Max visibility timeout:** 12 hours (default 30s)
- **Max messages per batch:** 10
- **Max queues per region:** 1,000,000 (soft limit)
- **FIFO throughput:** 3000 messages/sec with batching, 300/sec without

## Advanced Features
- **Dead-Letter Queues (DLQ):** For failed message processing
- **Long Polling:** Up to 20 seconds to reduce empty responses
- **Message Timers:** Delay delivery of individual messages
- **Batch Operations:** Send/receive/delete up to 10 messages at once
- **Server-Side Encryption (SSE):** Encrypt messages at rest
- **VPC Endpoints:** Private connectivity to SQS

## Performance Tuning
- Use long polling to reduce costs and latency
- Tune visibility timeout to match processing time
- Use DLQs for error handling and debugging
- Monitor queue metrics (age, depth, error rate) in CloudWatch
- Use batch operations for efficiency

## When to Use SQS
- Decoupling microservices, serverless, and distributed systems
- Buffering workloads and smoothing traffic spikes
- Asynchronous processing and event-driven architectures

## When NOT to Use SQS
- For publish/subscribe (use SNS or EventBridge)
- For strict ordering and exactly-once (use FIFO queues)
- For streaming data (use Kinesis)

## Exam Tips
- **Messages are not deleted automatically—must call DeleteMessage**
- **DLQs are essential for error analysis**
- **Visibility timeout too short = duplicate processing**
- **FIFO queues have throughput limits**
- **Long polling reduces cost and latency**

## Troubleshooting & Common Errors
- **Messages not deleted:** Ensure DeleteMessage is called after processing
- **Duplicate messages:** Increase visibility timeout or check processing logic
- **Access denied:** Check IAM policies and queue permissions
- **Queue not receiving messages:** Check queue policy, DLQ, and producer logic
- **High queue depth:** Scale consumers or check for processing bottlenecks

## Useful Links
- [SQS User Guide](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/)
- [SQS Limits](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/limits-messages-queues.html)
- [Best Practices](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-best-practices.html)

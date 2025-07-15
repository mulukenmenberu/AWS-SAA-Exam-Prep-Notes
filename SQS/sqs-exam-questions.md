# AWS SQS – Exam Questions

---
**Q1: What is the main benefit of using SQS?**
A) Real-time data analytics
B) Decoupling application components
C) Data storage
D) Database replication

**Answer:** B
**Explanation:** SQS decouples producers and consumers, improving reliability and scalability.

---
**Q2: What is a dead-letter queue (DLQ) in SQS?**
A) A queue for storing successfully processed messages
B) A queue for messages that can't be processed after multiple attempts
C) A queue for encrypted messages
D) A queue for high-priority messages

**Answer:** B
**Explanation:** DLQs store messages that failed processing after a set number of attempts.

---
**Q3: Which SQS queue type guarantees message order?**
A) Standard Queue
B) FIFO Queue
C) Dead-letter Queue
D) SNS Queue

**Answer:** B
**Explanation:** FIFO queues guarantee message order and exactly-once processing.

---
**Q4: How can you prevent duplicate message processing in SQS?**
A) Use visibility timeout
B) Use SNS
C) Use S3 triggers
D) Use IAM policies

**Answer:** A
**Explanation:** Visibility timeout hides a message after it's received, preventing duplicate processing.

---
**Q5: How can you trigger Lambda functions from SQS?**
A) Configure Lambda as an SQS event source
B) Use CloudWatch Events
C) Use S3 event notifications
D) Use Route 53 health checks

**Answer:** A
**Explanation:** Lambda can poll SQS and process messages automatically.

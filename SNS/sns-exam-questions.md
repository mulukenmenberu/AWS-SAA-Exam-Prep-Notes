# AWS SNS – Exam Questions

---
**Q1: What is the main use of SNS?**
A) File storage
B) Publish/subscribe messaging
C) Compute scaling
D) Database replication

**Answer:** B
**Explanation:** SNS is a pub/sub messaging service for application and user notifications.

---
**Q2: Which protocols can SNS deliver messages to? (Choose TWO)**
A) SQS
B) Lambda
C) RDS
D) EC2

**Answer:** A, B
**Explanation:** SNS can deliver messages to SQS, Lambda, HTTP/S, email, SMS, and mobile push endpoints.

---
**Q3: How can you filter messages sent to SNS subscribers?**
A) Use subscription filter policies
B) Use IAM policies
C) Use S3 bucket policies
D) Use VPC security groups

**Answer:** A
**Explanation:** Subscription filter policies allow fine-grained message routing.

---
**Q4: How can you ensure reliable message delivery in SNS?**
A) Use multiple protocols and monitor delivery status
B) Use S3 versioning
C) Use EC2 auto scaling
D) Use CloudTrail

**Answer:** A
**Explanation:** Using multiple protocols and monitoring delivery status increases reliability.

---
**Q5: What is a common use case for SNS and SQS integration?**
A) Fan-out messaging to multiple queues for parallel processing
B) Encrypting messages at rest
C) Real-time analytics
D) Database migration

**Answer:** A
**Explanation:** SNS can fan out messages to multiple SQS queues for parallel processing.

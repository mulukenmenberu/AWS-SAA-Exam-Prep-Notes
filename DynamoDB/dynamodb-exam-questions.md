# AWS DynamoDB – Exam Questions

---
**Q1: What is the main benefit of DynamoDB's On-Demand capacity mode?**
A) Manual scaling
B) Automatic scaling with pay-per-request pricing
C) Requires provisioned throughput
D) Only for test environments

**Answer:** B
**Explanation:** On-Demand mode automatically scales and charges only for actual read/write requests.

---
**Q2: How can you efficiently retrieve all orders for a specific user in DynamoDB?**
A) Use a partition key of UserID and a sort key of OrderID
B) Use a scan operation
C) Use S3 event notifications
D) Use Route 53 health checks

**Answer:** A
**Explanation:** Using a composite key (UserID + OrderID) allows efficient queries for all orders by user.

---
**Q3: What is a Global Secondary Index (GSI) used for?**
A) To enable queries on non-primary key attributes
B) To encrypt data
C) To store backups
D) To monitor CloudWatch metrics

**Answer:** A
**Explanation:** GSIs allow flexible queries on attributes other than the primary key.

---
**Q4: How can you trigger real-time processing when data changes in DynamoDB?**
A) Enable DynamoDB Streams and connect to Lambda
B) Use S3 event notifications
C) Use EC2 user data
D) Use Route 53 health checks

**Answer:** A
**Explanation:** DynamoDB Streams capture changes, and Lambda can process them in real time.

---
**Q5: What should you do if you see throttling errors in DynamoDB?**
A) Check for hot partitions, increase capacity, or switch to On-Demand mode
B) Ignore the errors
C) Delete the table
D) Use S3 event notifications

**Answer:** A
**Explanation:** Throttling is often caused by hot partitions or insufficient capacity.

---
**Q6: What is the maximum item size in DynamoDB?**
A) 4 KB
B) 400 KB
C) 4 MB
D) 40 MB

**Answer:** B
**Explanation:** The maximum item size in DynamoDB is 400 KB.

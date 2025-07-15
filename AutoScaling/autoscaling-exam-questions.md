# AWS Auto Scaling – Exam Questions

---
**Q1: What is an Auto Scaling Group (ASG)?**
A) A group of S3 buckets
B) A logical group of EC2 instances managed together
C) A set of IAM users
D) A collection of Lambda functions

**Answer:** B
**Explanation:** ASG manages a group of EC2 instances for scaling and health.

---
**Q2: How can you automatically replace unhealthy EC2 instances in an ASG?**
A) Enable health checks
B) Use S3 event notifications
C) Use Route 53 health checks
D) Use CloudTrail

**Answer:** A
**Explanation:** Health checks allow ASG to detect and replace unhealthy instances.

---
**Q3: What is predictive scaling?**
A) Scaling based on scheduled times
B) Scaling based on machine learning forecasts
C) Manual scaling
D) Scaling based on IAM policies

**Answer:** B
**Explanation:** Predictive scaling uses ML to forecast demand and scale in advance.

---
**Q4: How can you optimize costs with Auto Scaling?**
A) Use Spot Instances in ASGs
B) Use S3 event notifications
C) Use Route 53 health checks
D) Use EC2 user data

**Answer:** A
**Explanation:** Spot Instances provide significant cost savings in ASGs.

---
**Q5: What is a best practice for high availability in ASGs?**
A) Distribute instances across multiple AZs
B) Use a single AZ
C) Use S3 for storage
D) Use CloudTrail

**Answer:** A
**Explanation:** Spreading instances across AZs increases availability and fault tolerance.

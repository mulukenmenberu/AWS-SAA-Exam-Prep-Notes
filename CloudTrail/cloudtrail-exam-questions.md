# AWS CloudTrail – Exam Questions

---
**Q1: What is the main purpose of AWS CloudTrail?**
A) Real-time monitoring of EC2 instances
B) Logging and auditing all API calls and account activity
C) Managing IAM users
D) Encrypting S3 buckets

**Answer:** B
**Explanation:** CloudTrail records all API calls and account activity for auditing and security.

---
**Q2: How can you ensure CloudTrail logs all activity across all AWS regions?**
A) Create a trail and enable it for all regions
B) Use S3 event notifications
C) Use EC2 user data
D) Use Route 53 health checks

**Answer:** A
**Explanation:** Trails must be enabled for all regions to capture cross-region activity.

---
**Q3: What is a data event in CloudTrail?**
A) An event related to S3 object-level or Lambda function activity
B) An IAM policy change
C) A CloudWatch alarm
D) An EC2 instance launch

**Answer:** A
**Explanation:** Data events log S3 object-level and Lambda function activity (not enabled by default).

---
**Q4: How can you get notified of suspicious activity, such as root account usage?**
A) Set up CloudWatch Alarms on CloudTrail logs
B) Use S3 event notifications
C) Use Route 53 health checks
D) Use EC2 user data

**Answer:** A
**Explanation:** CloudWatch Alarms can notify you of critical events recorded by CloudTrail.

---
**Q5: What should you do to secure CloudTrail logs?**
A) Store logs in an encrypted S3 bucket with restricted access
B) Store logs in a public S3 bucket
C) Delete logs after 1 day
D) Use EC2 user data

**Answer:** A
**Explanation:** Logs should be encrypted and access-controlled to prevent tampering.

---
**Q6: How can you analyze CloudTrail logs for specific user activity?**
A) Use Athena or the CloudTrail console to search logs
B) Use S3 event notifications
C) Use Route 53 health checks
D) Use EC2 user data

**Answer:** A
**Explanation:** Athena and the CloudTrail console allow you to search and analyze logs by user, resource, or event type.

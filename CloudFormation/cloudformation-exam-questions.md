# AWS CloudFormation – Exam Questions

---
**Q1: What is the main benefit of using CloudFormation?**
A) Manual resource creation
B) Infrastructure as Code for repeatable, automated deployments
C) Real-time analytics
D) Database management

**Answer:** B
**Explanation:** CloudFormation enables Infrastructure as Code, making deployments repeatable and automated.

---
**Q2: How can you deploy the same stack to multiple AWS accounts and regions?**
A) Use StackSets
B) Use S3 event notifications
C) Use EC2 user data
D) Use Route 53 health checks

**Answer:** A
**Explanation:** StackSets allow you to deploy stacks across multiple accounts and regions.

---
**Q3: What is a change set in CloudFormation?**
A) A preview of changes before updating a stack
B) A set of IAM policies
C) A group of EC2 instances
D) A CloudWatch alarm

**Answer:** A
**Explanation:** Change sets let you preview what will change before applying updates to a stack.

---
**Q4: How can you make a CloudFormation template reusable for different environments?**
A) Use parameters
B) Use S3 bucket policies
C) Use EC2 security groups
D) Use Route 53 health checks

**Answer:** A
**Explanation:** Parameters allow you to pass in different values for each environment.

---
**Q5: What should you do if a stack update fails?**
A) Review the Events tab and error messages, then roll back or fix the template
B) Ignore the error
C) Delete all resources manually
D) Use S3 event notifications

**Answer:** A
**Explanation:** Always review errors, use rollback, and fix issues in the template or parameters.

---
**Q6: How can you detect if someone changed a resource outside of CloudFormation?**
A) Use drift detection
B) Use S3 event notifications
C) Use Route 53 health checks
D) Use EC2 user data

**Answer:** A
**Explanation:** Drift detection finds resources that have been changed outside of CloudFormation.

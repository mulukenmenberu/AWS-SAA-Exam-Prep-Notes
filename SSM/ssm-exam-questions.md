# AWS Systems Manager (SSM) – Exam Questions

---
**Q1: What is the main benefit of using SSM Run Command?**
A) Remotely execute commands/scripts on instances without SSH
B) Store objects in S3
C) Encrypt EBS volumes
D) Manage IAM users

**Answer:** A
**Explanation:** Run Command lets you securely run commands/scripts on managed instances without SSH.

---
**Q2: How can you securely store and retrieve secrets or configuration data in SSM?**
A) Use Parameter Store with encryption
B) Use S3 event notifications
C) Use EC2 user data
D) Use Route 53 health checks

**Answer:** A
**Explanation:** Parameter Store securely stores secrets/config with optional encryption.

---
**Q3: What is the purpose of SSM Patch Manager?**
A) Automate OS and software patching across your fleet
B) Store logs in S3
C) Manage IAM users
D) Encrypt S3 buckets

**Answer:** A
**Explanation:** Patch Manager automates patching for compliance and security.

---
**Q4: How can you access an EC2 instance without opening SSH ports?**
A) Use Session Manager
B) Use S3 event notifications
C) Use Route 53 health checks
D) Use EC2 user data

**Answer:** A
**Explanation:** Session Manager provides secure, auditable shell access without SSH.

---
**Q5: What should you check if an instance is not showing as managed in SSM?**
A) SSM Agent status and IAM role
B) S3 bucket policies
C) IAM user permissions
D) CloudTrail logs only

**Answer:** A
**Explanation:** The SSM Agent must be running and the instance must have the correct IAM role.

---
**Q6: How can you automate deployments or operational tasks with SSM?**
A) Use Automation documents
B) Use S3 event notifications
C) Use Route 53 health checks
D) Use EC2 user data

**Answer:** A
**Explanation:** Automation documents (playbooks) automate tasks like deployments, patching, and config changes.

# EC2 Model Exam Questions

---
**Q1:** What happens to data on an instance store when an EC2 instance is stopped?
- A) Data persists
- B) Data is lost
- C) Data is backed up to S3
- D) Data is snapshotted

**Answer:** B. Data is lost. Instance store is ephemeral.

---
**Q2:** Which EC2 pricing model offers the biggest discount but can be interrupted by AWS?
- A) On-Demand
- B) Reserved
- C) Spot
- D) Dedicated Host

**Answer:** C. Spot Instances can be interrupted and offer up to 90% discount.

---
**Q3:** How can you ensure an EC2 instance can access S3 securely without hardcoding credentials?
- A) Use IAM Role attached to the instance
- B) Store credentials in user data
- C) Use root account keys
- D) Use Security Groups

**Answer:** A. IAM Roles are the secure way.

---
**Q4:** What is the default limit of On-Demand EC2 instances per region?
- A) 5
- B) 10
- C) 20
- D) 50

**Answer:** C. 20 per region (can request increase).

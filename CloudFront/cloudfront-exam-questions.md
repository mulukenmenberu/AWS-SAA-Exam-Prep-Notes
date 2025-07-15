# AWS CloudFront – Exam Questions

---
**Q1: What is the primary benefit of using CloudFront?**
A) Data storage
B) Content delivery with low latency
C) Database management
D) Serverless compute

**Answer:** B
**Explanation:** CloudFront is a CDN that delivers content with low latency and high transfer speeds.

---
**Q2: How can you restrict access to content in CloudFront?**
A) Use signed URLs/cookies
B) Enable S3 versioning
C) Use EC2 security groups
D) Enable CloudTrail

**Answer:** A
**Explanation:** Signed URLs/cookies allow you to control who can access your content.

---
**Q3: Which AWS services can be used as CloudFront origins? (Choose TWO)**
A) S3
B) DynamoDB
C) EC2
D) RDS

**Answer:** A, C
**Explanation:** S3 and EC2 can both serve as CloudFront origins.

---
**Q4: How does CloudFront improve security for web applications?**
A) By integrating with AWS WAF and Shield
B) By encrypting EBS volumes
C) By enabling S3 bucket policies
D) By using IAM roles

**Answer:** A
**Explanation:** CloudFront can integrate with AWS WAF and Shield for enhanced security.

---
**Q5: What is the effect of a cache miss in CloudFront?**
A) The request is served from the origin
B) The request fails
C) The request is redirected to another region
D) The request is denied

**Answer:** A
**Explanation:** On a cache miss, CloudFront fetches the content from the origin and caches it.

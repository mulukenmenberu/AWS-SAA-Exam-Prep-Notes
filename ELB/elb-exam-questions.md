# AWS Elastic Load Balancing (ELB) – Exam Questions

---
**Q1: What is the main benefit of using an Application Load Balancer (ALB)?**
A) Layer 7 routing, host/path-based routing, and WebSocket support
B) Only supports TCP traffic
C) Only for legacy applications
D) No health checks

**Answer:** A
**Explanation:** ALB operates at Layer 7, supports advanced routing, and WebSockets.

---
**Q2: How does ELB improve application availability?**
A) Distributes traffic across healthy targets in multiple AZs
B) Stores data in S3
C) Encrypts EBS volumes
D) Manages IAM users

**Answer:** A
**Explanation:** ELB routes traffic only to healthy targets, improving availability and fault tolerance.

---
**Q3: Which ELB type is best for high-performance, low-latency TCP/UDP workloads?**
A) Application Load Balancer (ALB)
B) Network Load Balancer (NLB)
C) Classic Load Balancer (CLB)
D) Gateway Load Balancer (GWLB)

**Answer:** B
**Explanation:** NLB is designed for ultra-high performance and low-latency TCP/UDP traffic.

---
**Q4: How can you secure your application with ELB? (Choose TWO)**
A) Use ACM for SSL/TLS certificates
B) Enable AWS WAF for web protection
C) Use S3 event notifications
D) Use Route 53 health checks

**Answer:** A, B
**Explanation:** ACM provides SSL/TLS, and WAF protects against web attacks.

---
**Q5: What should you check if your targets are marked unhealthy by the load balancer?**
A) Health check configuration, security groups, and instance status
B) S3 bucket policies
C) IAM user permissions
D) CloudTrail logs only

**Answer:** A
**Explanation:** Health check settings, security groups, and instance health are common causes of unhealthy targets.

---
**Q6: What is cross-zone load balancing?**
A) Distributes traffic evenly across all targets in all enabled AZs
B) Encrypts data at rest
C) Stores logs in S3
D) Only for Classic Load Balancer

**Answer:** A
**Explanation:** Cross-zone load balancing ensures even traffic distribution across all AZs.

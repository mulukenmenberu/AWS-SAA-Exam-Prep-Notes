# VPC Model Exam Questions

---
**Q1:** What is required to allow instances in a private subnet to access the internet?
- A) Internet Gateway
- B) NAT Gateway
- C) VPC Peering
- D) VPC Endpoint

**Answer:** B. NAT Gateway allows outbound internet from private subnets.

---
**Q2:** Which VPC component is stateful?
- A) Security Group
- B) NACL
- C) Route Table
- D) Subnet

**Answer:** A. Security Groups are stateful, NACLs are stateless.

---
**Q3:** What prevents VPC peering between two VPCs?
- A) Overlapping CIDR blocks
- B) Different regions
- C) Different accounts
- D) No IGW

**Answer:** A. Overlapping CIDR blocks prevent peering.

---
**Q4:** How can you privately connect to S3 from a VPC?
- A) VPC Endpoint
- B) NAT Gateway
- C) VPN
- D) IGW

**Answer:** A. VPC Endpoint provides private connectivity to S3.

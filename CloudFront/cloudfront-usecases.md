# AWS CloudFront – Use Cases

## 1. Global Content Delivery
- **Scenario:** Deliver static and dynamic content (websites, videos, APIs) to users worldwide with low latency.
- **Best Practice:** Use multiple origins (S3, EC2, on-premises) and enable geo-restriction for compliance.

## 2. Securing Applications
- **Scenario:** Protect web applications from DDoS attacks and malicious traffic.
- **Best Practice:** Integrate with AWS WAF and Shield, enable HTTPS, and use signed URLs/cookies for private content.

## 3. API Acceleration
- **Scenario:** Distribute RESTful APIs globally for faster response times.
- **Best Practice:** Use Lambda@Edge for request/response manipulation and caching API responses.

## 4. Live & On-Demand Video Streaming
- **Scenario:** Stream video content to a global audience with minimal buffering.
- **Best Practice:** Use Media Services as origin, enable cache behaviors for different content types.

## 5. Software Distribution
- **Scenario:** Distribute software updates, patches, or large files efficiently.
- **Best Practice:** Use S3 as origin, enable versioning, and restrict access with signed URLs.

## 6. Multi-Region Redundancy
- **Scenario:** Ensure high availability by routing requests to healthy origins across regions.
- **Best Practice:** Use origin failover and health checks.

## 7. Compliance & Data Residency
- **Scenario:** Restrict content delivery to specific countries or regions.
- **Best Practice:** Use geo-restriction and custom error responses.

## Troubleshooting Tips
- Check cache hit/miss ratios in CloudFront reports.
- Use invalidations to remove outdated content.
- Monitor with CloudWatch metrics and alarms.

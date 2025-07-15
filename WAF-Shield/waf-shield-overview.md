# AWS WAF & Shield – Overview

## What is AWS WAF?
AWS Web Application Firewall (WAF) is a managed security service that protects web applications from common web exploits and bots that can affect availability, compromise security, or consume excessive resources. WAF lets you create custom rules to allow, block, or monitor (count) web requests based on conditions such as IP addresses, HTTP headers, HTTP body, URI strings, and more.

## What is AWS Shield?
AWS Shield is a managed Distributed Denial of Service (DDoS) protection service that safeguards applications running on AWS. There are two tiers:
- **Shield Standard:** Automatic protection for all AWS customers at no extra cost.
- **Shield Advanced:** Enhanced DDoS protection, 24/7 access to the AWS DDoS Response Team (DRT), advanced reporting, and financial protections.

## Key Features
- **Customizable Web Security:** Create rules to block common attacks (SQL injection, XSS, etc.).
- **Managed Rule Groups:** Pre-configured rules for common threats, maintained by AWS and partners.
- **Bot Control:** Detect and mitigate bot traffic.
- **Rate-Based Rules:** Limit requests from specific IPs to prevent abuse.
- **Real-Time Metrics & Logging:** Integrated with CloudWatch and Kinesis for monitoring and alerting.
- **DDoS Protection:** Automatic detection and mitigation of DDoS attacks with Shield.

## Architecture
- WAF is deployed on Amazon CloudFront, Application Load Balancer (ALB), API Gateway, or AWS App Runner.
- Shield operates at the AWS network edge, protecting all AWS resources.

## Advanced/Practical Context
- **Layered Security:** Combine WAF, Shield, and AWS Firewall Manager for comprehensive protection.
- **Automation:** Use AWS Lambda to automate responses to security events.
- **Compliance:** Helps meet PCI DSS, GDPR, and other regulatory requirements.

## Real-World Relevance
- Used by organizations of all sizes to protect public-facing web applications and APIs.
- Essential for e-commerce, financial services, healthcare, and any business with internet-facing workloads.

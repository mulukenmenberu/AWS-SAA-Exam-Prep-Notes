# Route 53 Cheatsheet (Beginner to Advanced)

## Creating a Hosted Zone and Record (Console)
1. Go to the Route 53 Dashboard in AWS Console
2. Click "Hosted zones" > "Create hosted zone"
3. Enter your domain name and type (public/private)
4. Add record sets (A, CNAME, MX, etc.) for your resources
5. (Optional) Set routing policy, health checks, and TTL
6. Update your domain registrar to use Route 53 name servers

## Common CLI Commands
- **List Hosted Zones:** `aws route53 list-hosted-zones`
- **Create Hosted Zone:** `aws route53 create-hosted-zone --name example.com --caller-reference 1234`
- **List Records:** `aws route53 list-resource-record-sets --hosted-zone-id ZONEID`
- **Change Record:** `aws route53 change-resource-record-sets --hosted-zone-id ZONEID --change-batch file://changes.json`
- **Create Health Check:** `aws route53 create-health-check --caller-reference 1234 --health-check-config ...`
- **Register Domain:** `aws route53domains register-domain --domain-name example.com --duration-in-years 1 --admin-contact ...`

## Important Limits & Defaults
- **Max hosted zones per account:** 500 (soft limit)
- **Max records per hosted zone:** 10,000
- **Max health checks per account:** 200
- **Max domain registrations per account:** 50 (soft limit)
- **TTL range:** 0–172800 seconds (2 days)

## Advanced Features
- **Routing policies:** Simple, weighted, latency, failover, geolocation, geoproximity, multi-value
- **Traffic Flow:** Visual editor for complex routing
- **DNSSEC:** Domain security (signs DNS records)
- **Query logging:** Log DNS queries to CloudWatch Logs
- **Alias records:** Point root domain to AWS resources (ELB, S3, CloudFront)

## When to Use Route 53
- Global DNS for AWS and non-AWS resources
- Domain registration and management
- Advanced routing and failover for high availability
- Integrating with ELB, CloudFront, S3, API Gateway

## When NOT to Use Route 53
- For internal-only DNS (use private hosted zones or on-premises DNS)
- For non-AWS domain registration if you need a specific TLD not supported by Route 53

## Exam Tips
- **Alias records allow root domain mapping to AWS resources**
- **Health checks enable DNS failover**
- **Weighted routing splits traffic by percentage**
- **Latency routing directs users to the closest region**
- **TTL impacts failover and propagation speed**

## Troubleshooting & Common Errors
- **DNS not resolving:** Check NS records, propagation, and TTL
- **Health check failed:** Check endpoint, protocol, and security group
- **CNAME at root not allowed:** Use Alias record
- **Propagation delay:** Wait for DNS to update globally

## Useful Links
- [Route 53 User Guide](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/)
- [Route 53 Limits](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/DNSLimitations.html)
- [Best Practices](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/best-practices.html)

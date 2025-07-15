# CloudFront Cheatsheet (Beginner to Advanced)

## Creating a CloudFront Distribution (Console)
1. Go to the CloudFront Dashboard in AWS Console
2. Click "Create Distribution"
3. Choose origin (S3, EC2, ELB, etc.)
4. Configure default behavior (cache policy, allowed methods, viewer protocol policy)
5. (Optional) Add additional behaviors for specific paths
6. Set up security (HTTPS, OAC, WAF, etc.)
7. Create distribution and use the provided domain name (or custom CNAME)

## Common CLI Commands
- **List Distributions:** `aws cloudfront list-distributions`
- **Create Distribution:** `aws cloudfront create-distribution --origin-domain-name mybucket.s3.amazonaws.com --default-root-object index.html`
- **Update Distribution:** `aws cloudfront update-distribution --id E1234567890 --distribution-config file://config.json`
- **Create Invalidation:** `aws cloudfront create-invalidation --distribution-id E1234567890 --paths /index.html /images/*`
- **Get Distribution Status:** `aws cloudfront get-distribution --id E1234567890`

## Important Limits & Defaults
- **Max distributions per account:** 2,000 (soft limit)
- **Max origins per distribution:** 25
- **Max behaviors per distribution:** 50
- **Max cache TTL:** 365 days
- **Invalidations:** First 1,000 paths/month free, then $0.005 per path
- **Max Lambda@Edge associations:** 4 per behavior

## Advanced Features
- **Lambda@Edge:** Run code at edge locations
- **Field-Level Encryption:** Encrypt sensitive data at the edge
- **Signed URLs/Cookies:** Restrict access to premium content
- **Origin Access Control (OAC):** Secure S3 origins (replaces OAI)
- **WAF & Shield:** DDoS and web application protection
- **HTTP/2 and IPv6 support**

## Performance Tuning
- Set appropriate cache TTLs for static vs. dynamic content
- Use cache policies to control what is cached (headers, cookies, query strings)
- Enable compression for text-based content
- Use regional edge caches for large files
- Monitor with CloudWatch metrics and alarms

## When to Use CloudFront
- Global CDN for static/dynamic websites, APIs, video streaming
- DDoS protection and WAF integration
- Secure content delivery with signed URLs/cookies
- Offload traffic from origin servers

## When NOT to Use CloudFront
- For private, internal-only content (unless using signed URLs/cookies)
- For workloads not requiring global distribution or caching

## Exam Tips
- **OAC is preferred for S3 origins (OAI is legacy)**
- **Invalidation requests are not free after 1,000/month**
- **Lambda@Edge enables custom logic at the edge**
- **Field-Level Encryption protects sensitive data**
- **Propagation delay for config changes (minutes)**

## Troubleshooting & Common Errors
- **Access Denied:** Check OAC/OAI, S3 bucket policy, and origin permissions
- **Content not updating:** Invalidate cache or reduce TTL
- **SSL/TLS errors:** Check certificate and viewer protocol policy
- **Slow performance:** Check cache hit ratio, origin latency, and edge location coverage
- **Lambda@Edge errors:** Check function logs in CloudWatch

## Useful Links
- [CloudFront User Guide](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/)
- [CloudFront Limits](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/cloudfront-limits.html)
- [Best Practices](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/best-practices.html)

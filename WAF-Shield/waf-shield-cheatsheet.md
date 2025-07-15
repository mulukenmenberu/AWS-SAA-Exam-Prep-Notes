# AWS WAF & Shield – Cheatsheet

## Key Facts
- **WAF:** Protects web apps from common exploits (SQLi, XSS, bots)
- **Shield:** DDoS protection (Standard = automatic, Advanced = enhanced + support)
- **Deploy on:** CloudFront, ALB, API Gateway, App Runner
- **Managed Rules:** Prebuilt, updated by AWS/partners
- **Bot Control:** Detects and mitigates bots

## Common CLI Commands
- List WebACLs: `aws wafv2 list-web-acls --scope CLOUDFRONT`
- Create WebACL: `aws wafv2 create-web-acl ...`
- Associate WebACL: `aws wafv2 associate-web-acl ...`
- List Rules: `aws wafv2 list-rules ...`

## Console Tips
- Use visual rule builder for custom rules
- Enable logging to S3/Kinesis for analysis
- Monitor metrics in CloudWatch

## Best Practices
- Start with AWS Managed Rules, then add custom rules
- Use rate-based rules to prevent brute force
- Enable Shield Advanced for mission-critical apps
- Regularly review logs for false positives/negatives
- Integrate with Firewall Manager for multi-account setups

## Troubleshooting
- Check CloudWatch metrics for spikes or anomalies
- Review WAF logs for blocked/allowed requests
- Adjust rule priorities to avoid unintended blocks
- Use AWS DDoS Response Team (DRT) with Shield Advanced for incident support

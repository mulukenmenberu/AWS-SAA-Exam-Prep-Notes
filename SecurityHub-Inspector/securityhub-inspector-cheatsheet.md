# AWS Security Hub & Inspector – Cheatsheet

## Key Facts
- **Security Hub:** Aggregates security findings, compliance checks, dashboards
- **Inspector:** Automated vulnerability scanning for EC2, Lambda, ECR
- **Integration:** Works with GuardDuty, Macie, Organizations, and third-party tools
- **Compliance:** Supports CIS, PCI DSS, and custom standards

## Common CLI Commands
- List findings: `aws securityhub get-findings`
- Enable Security Hub: `aws securityhub enable-security-hub`
- Start Inspector scan: `aws inspector2 start-assessment-run ...`
- List Inspector findings: `aws inspector2 list-findings`

## Console Tips
- Use Security Hub insights for prioritized findings
- Enable automated compliance standards
- Set up integrations with Lambda for remediation

## Best Practices
- Enable Security Hub and Inspector across all accounts
- Regularly review and remediate high-severity findings
- Automate responses with Lambda and SSM Automation
- Use tags and filters to organize findings

## Troubleshooting
- Check IAM permissions for cross-account aggregation
- Review Inspector agent status on EC2
- Monitor CloudWatch metrics for scan results and errors

# AWS Systems Manager (SSM) – Cheatsheet

## Key Facts
- **Unified Management:** Manage EC2, on-premises, and hybrid resources
- **Run Command:** Remotely execute commands/scripts
- **Automation:** Automate patching, deployments, and config changes
- **Patch Manager:** Automate OS/software patching
- **Parameter Store:** Securely store/retrieve secrets and config
- **Session Manager:** Secure, auditable shell access (no SSH needed)
- **Inventory:** Collect/query software/hardware inventory
- **State Manager:** Enforce desired state/configuration
- **OpsCenter:** Centralized operational issues dashboard

## Common CLI Commands
- List managed instances: `aws ssm describe-instance-information`
- Run command: `aws ssm send-command --instance-ids i-123 --document-name AWS-RunShellScript --parameters commands=uptime`
- Start session: `aws ssm start-session --target i-123`
- Get parameter: `aws ssm get-parameter --name /my/secret --with-decryption`
- List documents: `aws ssm list-documents`
- Describe patch groups: `aws ssm describe-patch-groups`

## Console Tips
- Use "Quick Setup" for fast onboarding
- Use Session Manager for browser-based shell access
- Use Patch Manager to automate patching schedules
- Use Parameter Store for secrets/config in Lambda/EC2
- Monitor compliance and inventory in the dashboard

## Best Practices
- Assign the correct IAM role to all managed instances
- Use Parameter Store for all secrets/config (enable encryption)
- Enable logging for auditing and compliance
- Use Automation documents for repeatable tasks
- Regularly patch and inventory all resources

## Troubleshooting
- If an instance is not managed, check SSM Agent status and IAM role
- For command failures, review output and logs in the console
- For session issues, check VPC endpoints and security groups
- Use CloudWatch and AWS Config for monitoring and compliance

## Practical Tips
- Use SSM for zero-trust, no-SSH management
- Integrate with Lambda/EventBridge for event-driven automation
- Use Parameter Store versioning for config rollbacks
- Use State Manager to enforce baseline configurations

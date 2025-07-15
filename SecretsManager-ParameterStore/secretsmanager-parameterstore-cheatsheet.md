# AWS Secrets Manager & Parameter Store – Cheatsheet

## Key Facts
- **Secrets Manager:** Secure storage, automatic rotation, audit logging
- **Parameter Store:** Hierarchical config storage, supports plain/encrypted values
- **Encryption:** Both use AWS KMS for encryption at rest
- **Integration:** Works with EC2, Lambda, ECS, CodePipeline, etc.

## Common CLI Commands
- List secrets: `aws secretsmanager list-secrets`
- Get secret value: `aws secretsmanager get-secret-value --secret-id <name>`
- Put parameter: `aws ssm put-parameter --name <name> --value <value> --type SecureString`
- Get parameter: `aws ssm get-parameter --name <name> --with-decryption`

## Console Tips
- Use Lambda rotation templates in Secrets Manager
- Organize Parameter Store values with path hierarchies (e.g., /app/dev/db-password)
- Enable CloudTrail logging for auditing

## Best Practices
- Use Secrets Manager for sensitive credentials and enable automatic rotation
- Use Parameter Store for application config and feature flags
- Apply least privilege IAM policies for access
- Tag secrets/parameters for environment and usage tracking

## Troubleshooting
- Check IAM permissions for access errors
- Monitor secret rotation status in Secrets Manager
- Use CloudWatch metrics for usage and error tracking

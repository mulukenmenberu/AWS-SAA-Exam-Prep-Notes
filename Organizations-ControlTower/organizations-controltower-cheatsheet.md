# AWS Organizations & Control Tower – Cheatsheet

## Key Facts
- **Organizations:** Centralized multi-account management, consolidated billing
- **Control Tower:** Automated landing zone, account factory, guardrails
- **SCPs:** Enforce permissions and compliance
- **OUs:** Organize accounts by function, environment, or business unit

## Common CLI Commands
- List accounts: `aws organizations list-accounts`
- Create account: `aws organizations create-account --email <email> --account-name <name>`
- List OUs: `aws organizations list-organizational-units-for-parent --parent-id <id>`
- Attach SCP: `aws organizations attach-policy --policy-id <id> --target-id <account or OU>`

## Console Tips
- Use Account Factory in Control Tower for automated account provisioning
- Apply guardrails for security and compliance
- Monitor account activity with CloudTrail and AWS Config

## Best Practices
- Use OUs to separate production, dev, and sandbox accounts
- Apply least privilege with SCPs
- Enable centralized billing and cost allocation tags
- Regularly review guardrail compliance in Control Tower

## Troubleshooting
- Check SCPs for denied actions
- Monitor account creation logs in Control Tower
- Use AWS Config for compliance drift detection

# IAM Cheatsheet (Beginner-Friendly)

## Creating a User (Console)
1. Go to the IAM Dashboard in AWS Console.
2. Click "Users" > "Add user".
3. Enter username, select access type (console, programmatic, or both).
4. Attach policies directly or add to a group.
5. (Optional) Enable MFA.
6. Download credentials and share securely.

## Common CLI Commands
- **List Users:** `aws iam list-users`
- **Create User:** `aws iam create-user --user-name myuser`
- **Attach Policy:** `aws iam attach-user-policy --user-name myuser --policy-arn arn:aws:iam::aws:policy/AdministratorAccess`
- **Create Group:** `aws iam create-group --group-name mygroup`
- **Add User to Group:** `aws iam add-user-to-group --user-name myuser --group-name mygroup`
- **Create Role:** `aws iam create-role --role-name myrole --assume-role-policy-document file://trust.json`
- **Attach Role Policy:** `aws iam attach-role-policy --role-name myrole --policy-arn arn:aws:iam::aws:policy/AmazonS3FullAccess`

## Important Limits & Defaults
- **Users per account:** 5,000
- **Groups per account:** 1,000
- **Roles per account:** 2,500
- **Managed policies per user/group/role:** 10
- **Max policy size:** 6,144 characters

## When to Use IAM
- To control access for people and applications
- To grant AWS services permissions (via roles)
- To enforce security best practices (MFA, least privilege)

## When NOT to Use IAM
- For temporary, one-off access (use roles or temporary credentials)
- For external identity providers (use Cognito, SSO, or federated login)

## Exam Tips
- **IAM is global, not region-specific**
- **Root user should be locked down and never used for daily tasks**
- **MFA is highly recommended for all users**
- **Use groups to manage permissions for multiple users**
- **Use IAM roles for EC2, Lambda, and cross-account access**

## Troubleshooting & Common Errors
- **Access Denied:** Check policy, group, and role permissions
- **User can't log in:** Check access type and password policy
- **Policy not working:** Validate JSON syntax and resource ARNs
- **Too many permissions:** Use least privilege principle

## Useful Links
- [IAM User Guide](https://docs.aws.amazon.com/IAM/latest/UserGuide/)
- [IAM Best Practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html)
- [IAM Limits](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_iam-quotas.html)

# AWS Secrets Manager & Parameter Store – Overview

## What is AWS Secrets Manager?
AWS Secrets Manager is a managed service for securely storing, managing, and rotating sensitive information such as database credentials, API keys, and other secrets. It provides automatic rotation, fine-grained access control, and audit logging.

## What is AWS Systems Manager Parameter Store?
Parameter Store is a secure, hierarchical storage for configuration data management and secrets management. It supports both plain text and encrypted values, and is integrated with AWS IAM and KMS for access control and encryption.

## Key Features
- **Secure Storage:** Both services encrypt secrets at rest with AWS KMS.
- **Automatic Rotation:** Secrets Manager can automatically rotate secrets using Lambda.
- **Access Control:** Fine-grained permissions with IAM policies.
- **Audit Logging:** All access is logged in AWS CloudTrail.
- **Integration:** Easily integrates with EC2, Lambda, ECS, and other AWS services.
- **Parameter Hierarchies:** Parameter Store supports hierarchical organization for config management.

## Architecture
- **Secrets Manager:** Centralized secret storage, integrates with Lambda for rotation, and supports cross-account access.
- **Parameter Store:** Hierarchical key-value store, supports versioning and tagging.

## Advanced/Practical Context
- Use Secrets Manager for sensitive credentials and automatic rotation.
- Use Parameter Store for application configuration, feature flags, and less sensitive data.
- Both services support automation and CI/CD integration.

## Real-World Relevance
- Essential for secure DevOps, compliance, and reducing the risk of credential leaks.
- Used by organizations to centralize and automate secret management across environments.

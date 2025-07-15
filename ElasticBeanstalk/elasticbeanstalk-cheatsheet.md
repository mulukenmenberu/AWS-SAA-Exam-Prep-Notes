# Elastic Beanstalk Cheatsheet (Beginner to Advanced)

## Deploying an App (Console)
1. Go to the Elastic Beanstalk Dashboard in AWS Console
2. Click "Create Application"
3. Choose platform (e.g., Node.js, Python, Docker)
4. Upload your code or connect to a repository
5. Configure environment (instance type, scaling, VPC, etc.)
6. Launch environment and monitor health

## Common CLI Commands
- **List Applications:** `aws elasticbeanstalk describe-applications`
- **Create Application:** `aws elasticbeanstalk create-application --application-name MyApp`
- **Create Environment:** `aws elasticbeanstalk create-environment --application-name MyApp --environment-name MyEnv --solution-stack-name "64bit Amazon Linux 2 v3.3.6 running Node.js 14" --version-label v1`
- **Deploy New Version:** `aws elasticbeanstalk create-application-version --application-name MyApp --version-label v2 --source-bundle S3Bucket=mybucket,S3Key=app.zip`
- **Update Environment:** `aws elasticbeanstalk update-environment --environment-name MyEnv --version-label v2`
- **Terminate Environment:** `aws elasticbeanstalk terminate-environment --environment-name MyEnv`

## Important Limits & Defaults
- **Max applications per account:** 75
- **Max environments per application:** 200
- **Max environment name length:** 23 characters
- **Max environment variables:** 100
- **Max configuration files:** 50 per environment
- **Max deployment bundle size:** 512 MB (S3)

## Advanced Features
- **Immutable and blue/green deployments:** Zero downtime
- **.ebextensions:** Advanced configuration and automation
- **Custom platforms:** Build your own with Docker or Packer
- **Environment variables:** For secrets and config
- **Log streaming:** To S3 and CloudWatch
- **Integration with CodePipeline for CI/CD**

## Performance Tuning
- Use rolling/immutable/blue-green deployments for high availability
- Monitor health and set up CloudWatch alarms
- Use environment variables for configuration
- Regularly update platform versions for security
- Harden security groups and restrict access

## When to Use Elastic Beanstalk
- Web apps, APIs, and background workers needing managed infrastructure
- Teams wanting to focus on code, not infrastructure
- Rapid prototyping and deployment

## When NOT to Use Elastic Beanstalk
- For full control over every infrastructure detail (use ECS/EKS/EC2 directly)
- For serverless-only workloads (use Lambda)
- For highly specialized or legacy stacks not supported by Beanstalk

## Exam Tips
- **Immutable and blue/green deployments = zero downtime**
- **.ebextensions for advanced config**
- **Health monitoring is built-in**
- **Environments can be web server or worker (SQS)**
- **Logs are not retained by default—enable log streaming**

## Troubleshooting & Common Errors
- **Deployment failed:** Check logs in S3/CloudWatch and event history
- **App not reachable:** Check security groups, load balancer, and health status
- **Environment stuck updating:** Check configuration and rollback if needed
- **Customizations lost:** Use .ebextensions and version control
- **High costs:** Review instance types, scaling settings, and unused environments

## Useful Links
- [Elastic Beanstalk User Guide](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/Welcome.html)
- [Elastic Beanstalk Limits](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/limits.html)
- [Best Practices](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/using-features.managing.env-tiers.html)

# Lambda Cheatsheet (Beginner-Friendly)

## Creating a Lambda Function (Console)
1. Go to the Lambda Dashboard in AWS Console.
2. Click "Create function".
3. Choose "Author from scratch" or use a blueprint.
4. Name your function, select runtime (e.g., Python 3.9).
5. Set permissions (create or use an IAM role).
6. Write or upload your code.
7. Add a trigger (e.g., S3, API Gateway).
8. Test your function with sample events.

## Common CLI Commands
- **List Functions:** `aws lambda list-functions`
- **Create Function:** `aws lambda create-function --function-name my-func --runtime python3.9 --role arn:aws:iam::123456789012:role/lambda-role --handler lambda_function.lambda_handler --zip-file fileb://function.zip`
- **Update Code:** `aws lambda update-function-code --function-name my-func --zip-file fileb://code.zip`
- **Invoke Function:** `aws lambda invoke --function-name my-func output.txt`
- **Add Permission:** `aws lambda add-permission --function-name my-func --action lambda:InvokeFunction --principal s3.amazonaws.com --source-arn arn:aws:s3:::my-bucket`

## Important Limits & Defaults
- **Max execution time:** 15 minutes per invocation
- **Memory:** 128 MB to 10,240 MB
- **Package size:** 50 MB (zipped), 250 MB (unzipped)
- **Environment variables:** 4 KB
- **Concurrent executions:** 1,000 (soft limit)
- **Max event payload:** 6 MB (synchronous), 256 KB (async)

## When to Use Lambda
- Event-driven tasks (file uploads, API requests, scheduled jobs)
- Serverless APIs (with API Gateway)
- Automation and glue code
- Data processing and transformation

## When NOT to Use Lambda
- Long-running jobs (>15 minutes)
- Applications needing persistent local storage
- High-performance computing (use EC2/ECS)

## Exam Tips
- **Lambda is stateless**
- **Max execution time is 15 minutes**
- **IAM roles are required for resource access**
- **Cold starts can add latency**
- **Use Layers for shared code/libraries**

## Troubleshooting & Common Errors
- **Timeouts:** Increase timeout or optimize code
- **Access Denied:** Check IAM role permissions
- **Function not triggered:** Check event source mapping and permissions
- **Package too large:** Use Layers or reduce dependencies

## Useful Links
- [Lambda User Guide](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html)
- [Lambda Limits](https://docs.aws.amazon.com/lambda/latest/dg/gettingstarted-limits.html)
- [Serverless Best Practices](https://docs.aws.amazon.com/lambda/latest/dg/best-practices.html)

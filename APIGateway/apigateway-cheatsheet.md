# AWS API Gateway – Cheatsheet

## Key Facts
- **API Types:** REST, HTTP, WebSocket
- **Integrations:** Lambda, HTTP, AWS services, Mock
- **Security:** IAM, Cognito, Lambda authorizers, API keys
- **Deployment:** Edge-optimized, regional, private

## Common CLI Commands
- List APIs: `aws apigateway get-rest-apis`
- Create API: `aws apigateway create-rest-api --name <name>`
- Deploy API: `aws apigateway create-deployment --rest-api-id <id> --stage-name <stage>`
- List resources: `aws apigateway get-resources --rest-api-id <id>`

## Console Tips
- Use stages for versioning and safe deployments
- Enable CloudWatch logging for monitoring
- Set up usage plans and API keys for rate limiting

## Best Practices
- Use request/response validation to catch errors early
- Enable caching for frequently accessed endpoints
- Secure APIs with IAM, Cognito, or Lambda authorizers
- Use throttling and quotas to protect backends

## Troubleshooting
- Check CloudWatch logs for errors
- Use mapping templates to debug request/response transformations
- Monitor API Gateway metrics for latency and error rates

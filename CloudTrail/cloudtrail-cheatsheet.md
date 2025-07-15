# AWS CloudTrail – Cheatsheet

## Key Facts
- **API Logging:** Records all API calls and account activity
- **Event History:** View last 90 days in the console
- **Trails:** Configure to log events across all regions and deliver to S3
- **Data Events:** Log S3 object-level and Lambda function activity (not enabled by default)
- **Insights:** Detect unusual activity patterns
- **Integration:** Works with CloudWatch, Athena, GuardDuty
- **Encryption:** Logs are encrypted in S3 (optionally with KMS)

## Common CLI Commands
- List trails: `aws cloudtrail list-trails`
- Create trail: `aws cloudtrail create-trail --name my-trail --s3-bucket-name my-bucket`
- Start logging: `aws cloudtrail start-logging --name my-trail`
- Lookup events: `aws cloudtrail lookup-events --lookup-attributes AttributeKey=Username,AttributeValue=<user>`
- Get event selectors: `aws cloudtrail get-event-selectors --trail-name my-trail`
- Add data event logging: `aws cloudtrail put-event-selectors --trail-name my-trail --event-selectors '[{"ReadWriteType":"All","IncludeManagementEvents":true,"DataResources":[{"Type":"AWS::S3::Object","Values":["arn:aws:s3:::my-bucket/"]}]}]'`

## Console Tips
- Use the "Event history" tab for quick searches
- Set up trails to log across all regions (recommended)
- Send logs to CloudWatch for real-time monitoring and alerts
- Use Athena to query logs for advanced analysis

## Best Practices
- Enable trails in all regions to avoid missing activity
- Secure S3 buckets that store logs (use bucket policies and encryption)
- Set up CloudWatch Alarms for critical events (e.g., root login, policy changes)
- Enable data event logging for S3 and Lambda if needed
- Regularly review logs for suspicious activity

## Troubleshooting
- If logs are missing, check trail status and S3 bucket permissions
- Use CloudTrail Insights to investigate unusual activity
- Check CloudWatch for alerts on critical events
- Use Athena for deep log analysis if needed

## Practical Tips
- Use multiple trails for different teams or compliance needs
- Rotate S3 log bucket keys regularly for security
- Integrate with GuardDuty for automated threat detection

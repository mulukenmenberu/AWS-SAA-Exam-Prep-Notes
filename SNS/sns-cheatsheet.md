# SNS Cheatsheet (Beginner to Advanced)

## Creating a Topic and Subscription (Console)
1. Go to the SNS Dashboard in AWS Console
2. Click "Create topic" (Standard or FIFO)
3. Configure topic settings (name, display name, encryption, access policy)
4. Create the topic and note the ARN
5. Click "Create subscription", choose protocol (SQS, Lambda, email, etc.), and enter endpoint
6. Confirm subscription if required (email, HTTP/S)

## Common CLI Commands
- **List Topics:** `aws sns list-topics`
- **Create Topic:** `aws sns create-topic --name MyTopic`
- **Subscribe:** `aws sns subscribe --topic-arn arn:aws:sns:... --protocol email --notification-endpoint user@example.com`
- **Publish Message:** `aws sns publish --topic-arn arn:aws:sns:... --message "Hello"`
- **List Subscriptions:** `aws sns list-subscriptions-by-topic --topic-arn arn:aws:sns:...`
- **Set Topic Attributes:** `aws sns set-topic-attributes --topic-arn ... --attribute-name DisplayName --attribute-value "My Notifications"`

## Important Limits & Defaults
- **Max topics per account:** 100,000 (soft limit)
- **Max subscriptions per topic:** 12,500
- **Max message size:** 256 KB
- **Max filter policies per subscription:** 5
- **Max message delivery retries:** 100 (HTTP/S)
- **FIFO throughput:** 300 messages/sec (with batching), 10/sec (without)

## Advanced Features
- **Message filtering:** Deliver only relevant messages to each subscriber
- **Raw message delivery:** Send unmodified messages to SQS/Lambda
- **Delivery status logging:** Monitor delivery success/failure
- **Mobile push notifications:** Integrate with APNS, FCM, ADM, Baidu
- **VPC endpoints:** Private connectivity to SNS
- **Encryption:** At rest (KMS) and in transit (TLS)

## Performance Tuning
- Use message filtering to reduce unnecessary processing
- Enable delivery status logging for troubleshooting
- Use raw message delivery for SQS/Lambda
- Monitor delivery metrics and errors in CloudWatch
- Use FIFO topics for strict ordering and deduplication

## When to Use SNS
- Pub/sub messaging (fan-out)
- Event-driven architectures and microservices
- Mobile push, email, SMS, and HTTP/S notifications
- Integrating AWS services (Lambda, SQS, CloudWatch, EventBridge)

## When NOT to Use SNS
- For message persistence (use SQS for guaranteed delivery)
- For streaming data (use Kinesis)
- For direct point-to-point messaging (use SQS or EventBridge)

## Exam Tips
- **SNS is pub/sub, SQS is point-to-point**
- **SNS does not persist messages if delivery fails (except SQS/Lambda)**
- **Message filtering reduces unnecessary processing**
- **FIFO topics require FIFO subscriptions**
- **IAM and topic policies must allow both publisher and subscriber actions**

## Troubleshooting & Common Errors
- **No delivery to endpoint:** Check subscription confirmation, endpoint status, and retry policy
- **Access denied:** Check IAM and topic policies
- **Message not filtered correctly:** Check filter policy syntax
- **SMS/email not received:** Check provider limits and opt-in status
- **High delivery latency:** Check endpoint health and retry settings

## Useful Links
- [SNS User Guide](https://docs.aws.amazon.com/sns/latest/dg/welcome.html)
- [SNS Limits](https://docs.aws.amazon.com/sns/latest/dg/sns-limits.html)
- [Best Practices](https://docs.aws.amazon.com/sns/latest/dg/sns-best-practices.html)

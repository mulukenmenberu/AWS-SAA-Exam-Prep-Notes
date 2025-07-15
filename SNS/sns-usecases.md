# AWS SNS – Use Cases

## 1. Application-to-Application Messaging
- **Scenario:** Decouple microservices by sending notifications between distributed systems.
- **Best Practice:** Use message filtering to route messages to specific subscribers.

## 2. Application-to-Person Notifications
- **Scenario:** Send SMS, email, or mobile push notifications to users.
- **Best Practice:** Use platform endpoints for mobile push and enable delivery status logging.

## 3. Fan-Out Architecture
- **Scenario:** Distribute a single message to multiple SQS queues, Lambda functions, or HTTP endpoints.
- **Best Practice:** Use SNS topics to fan out events for parallel processing.

## 4. Event-Driven Workflows
- **Scenario:** Trigger automated workflows in response to application events (e.g., order placed, file uploaded).
- **Best Practice:** Integrate with Lambda and Step Functions for orchestration.

## 5. Monitoring and Alerting
- **Scenario:** Send alerts from CloudWatch Alarms to operations teams via SMS or email.
- **Best Practice:** Use multiple protocols for redundancy and reliability.

## Troubleshooting Tips
- Check subscription filter policies for correct message routing.
- Monitor delivery status and retry policies.
- Use CloudWatch metrics for message delivery failures.

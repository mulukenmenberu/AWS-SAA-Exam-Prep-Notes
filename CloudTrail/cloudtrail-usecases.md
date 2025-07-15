# AWS CloudTrail – Use Cases

## 1. Security Auditing
- **Scenario:** Track all API calls to detect unauthorized or suspicious activity.
- **Best Practice:** Set up CloudWatch Alarms for critical events (e.g., root login, policy changes).

## 2. Compliance Reporting
- **Scenario:** Prove to auditors that your AWS environment meets regulatory requirements (PCI DSS, HIPAA, etc.).
- **Best Practice:** Store logs in a secure, encrypted S3 bucket with access controls.

## 3. Incident Investigation
- **Scenario:** Investigate security incidents by tracing actions back to specific users or services.
- **Best Practice:** Use Athena or the CloudTrail console to search logs by user, resource, or event type.

## 4. Operational Troubleshooting
- **Scenario:** Diagnose why a resource was deleted or modified unexpectedly.
- **Best Practice:** Use the "Event history" tab to quickly find relevant events.

## 5. Data Access Monitoring
- **Scenario:** Monitor S3 object-level access or Lambda function invocations for sensitive data.
- **Best Practice:** Enable data event logging for S3 and Lambda, and review logs regularly.

## 6. Forensics and Root Cause Analysis
- **Scenario:** After a breach or outage, reconstruct the sequence of events leading up to the incident.
- **Best Practice:** Retain logs for the required period and use Insights to detect unusual activity patterns.

## Troubleshooting Tips
- If logs are missing, check trail status and S3 bucket permissions.
- Use CloudTrail Insights to spot anomalies.
- Regularly review and rotate S3 log bucket keys for security.
- Use multiple trails for different teams or compliance needs.

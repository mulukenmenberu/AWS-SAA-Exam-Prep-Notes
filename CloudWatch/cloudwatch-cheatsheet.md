# CloudWatch Cheatsheet (Beginner to Advanced)

## Setting Up Monitoring (Console)
1. Go to the CloudWatch Dashboard in AWS Console
2. View metrics for your AWS resources (EC2, Lambda, etc.)
3. Create custom dashboards to visualize key metrics
4. Set up alarms for critical metrics (e.g., CPU > 80%)
5. Enable log collection for applications and AWS services
6. Use metric filters and Contributor Insights for advanced analysis

## Common CLI Commands
- **List Metrics:** `aws cloudwatch list-metrics`
- **Get Metric Data:** `aws cloudwatch get-metric-data --metric-data-queries file://queries.json`
- **Put Custom Metric:** `aws cloudwatch put-metric-data --namespace MyApp --metric-name PageViews --value 1`
- **Create Alarm:** `aws cloudwatch put-metric-alarm --alarm-name HighCPU --metric-name CPUUtilization --namespace AWS/EC2 --statistic Average --period 300 --threshold 80 --comparison-operator GreaterThanThreshold --evaluation-periods 2 --alarm-actions arn:aws:sns:...`
- **Describe Alarms:** `aws cloudwatch describe-alarms`
- **Put Log Events:** `aws logs put-log-events --log-group-name MyGroup --log-stream-name MyStream --log-events file://events.json`
- **Create Log Group:** `aws logs create-log-group --log-group-name MyGroup`

## Important Limits & Defaults
- **Max dashboards per account:** 500
- **Max metrics per dashboard:** 50
- **Max custom metrics per account:** 10,000 (soft limit)
- **Max log group retention:** Indefinite (set retention policy to control costs)
- **Max alarms per region:** 5,000 (soft limit)
- **Max log event size:** 256 KB

## Advanced Features
- **Composite alarms:** Combine multiple alarms for complex alerting
- **Anomaly detection:** Machine learning-based thresholds
- **Contributor Insights:** Analyze high-cardinality log data
- **Synthetics:** Monitor endpoints with canaries
- **ServiceLens & X-Ray:** Distributed tracing and service maps
- **Metric math:** Perform calculations on metrics

## Performance Tuning
- Use detailed monitoring for critical resources (1-min granularity)
- Set log retention policies to control costs
- Use metric filters for real-time log-based metrics
- Use dashboards for at-a-glance health checks
- Monitor custom metrics for app-specific KPIs

## When to Use CloudWatch
- Monitoring AWS resources and custom applications
- Automated alerting and remediation
- Log aggregation, analysis, and retention
- Distributed tracing and troubleshooting

## When NOT to Use CloudWatch
- For on-premises-only monitoring (unless using hybrid/agent)
- For deep APM (use X-Ray or third-party tools for code-level tracing)

## Exam Tips
- **Alarms can trigger SNS, Auto Scaling, EC2 actions, etc.**
- **Composite alarms reduce alert noise**
- **Synthetics and Contributor Insights are billed separately**
- **Log ingestion and retention can incur significant costs**
- **Custom metrics are user-defined and incur charges**

## Troubleshooting & Common Errors
- **No data in metrics:** Check resource monitoring settings and data frequency
- **Alarm not triggering:** Check threshold, evaluation periods, and metric data
- **Log ingestion delays:** Check log agent status and network connectivity
- **High costs:** Review log retention, custom metrics, and data volume
- **Permission denied:** Check IAM policies for CloudWatch and Logs

## Useful Links
- [CloudWatch User Guide](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/)
- [CloudWatch Logs](https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/WhatIsCloudWatchLogs.html)
- [CloudWatch Limits](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/cloudwatch_limits.html)

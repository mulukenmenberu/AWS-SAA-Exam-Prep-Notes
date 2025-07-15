# AWS Auto Scaling – Cheatsheet

## Key Facts
- **Auto Scaling Group (ASG):** Manages EC2 instances
- **Scaling Policies:** Target tracking, step, scheduled
- **Predictive Scaling:** Forecasts and scales in advance
- **Health Checks:** Replaces unhealthy instances
- **Integration:** Works with ELB, CloudWatch, SNS

## Common CLI Commands
- List ASGs: `aws autoscaling describe-auto-scaling-groups`
- Create ASG: `aws autoscaling create-auto-scaling-group ...`
- Update ASG: `aws autoscaling update-auto-scaling-group ...`
- Set scaling policy: `aws autoscaling put-scaling-policy ...`

## Console Tips
- Use launch templates for flexibility
- Set up CloudWatch alarms for scaling triggers
- Monitor instance health and scaling activity

## Best Practices
- Use target tracking for simple, effective scaling
- Combine On-Demand and Spot Instances for cost savings
- Set minimum and maximum instance limits
- Use lifecycle hooks for custom actions during scaling

## Troubleshooting
- Check scaling activity history for errors
- Review CloudWatch metrics for scaling triggers
- Ensure health checks are configured correctly

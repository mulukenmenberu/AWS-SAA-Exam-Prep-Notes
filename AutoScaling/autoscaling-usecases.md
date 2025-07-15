# AWS Auto Scaling – Use Cases

## 1. Web Application Scaling
- **Scenario:** Automatically scale EC2 instances for a web app based on CPU utilization.
- **Best Practice:** Use target tracking scaling policy with CloudWatch alarms.

## 2. Batch Processing
- **Scenario:** Scale out compute resources for batch jobs and scale in when jobs complete.
- **Best Practice:** Use scheduled scaling for predictable workloads.

## 3. Cost Optimization
- **Scenario:** Use Spot Instances in ASGs to reduce compute costs.
- **Best Practice:** Set up mixed instance policies and fallback to On-Demand.

## 4. High Availability
- **Scenario:** Maintain minimum number of healthy instances across multiple AZs.
- **Best Practice:** Distribute ASG across at least two Availability Zones.

## 5. Microservices Scaling
- **Scenario:** Scale ECS tasks or Aurora Replicas based on demand.
- **Best Practice:** Use Application Auto Scaling for non-EC2 resources.

## Troubleshooting Tips
- Check scaling activity history for failed actions.
- Review CloudWatch metrics for scaling triggers.
- Ensure health checks are set to ELB for load-balanced apps.

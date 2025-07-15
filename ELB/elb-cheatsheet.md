# AWS Elastic Load Balancing (ELB) – Cheatsheet

## Key Facts
- **Types:** Application (ALB), Network (NLB), Gateway (GWLB), Classic (CLB)
- **Targets:** EC2, containers, Lambda, IP addresses
- **Cross-Zone Load Balancing:** Distributes traffic across all AZs
- **Health Checks:** Only routes to healthy targets
- **SSL/TLS:** Offload SSL at the load balancer
- **Sticky Sessions:** Session affinity for ALB/CLB
- **Access Logs:** Store request logs in S3
- **WebSocket Support:** ALB supports real-time communication
- **Security:** Integrates with WAF, ACM, Shield

## Common CLI Commands
- List load balancers: `aws elbv2 describe-load-balancers`
- Create ALB: `aws elbv2 create-load-balancer --name my-alb --subnets subnet-123 subnet-456 --security-groups sg-123`
- Create target group: `aws elbv2 create-target-group --name my-tg --protocol HTTP --port 80 --vpc-id vpc-123`
- Register targets: `aws elbv2 register-targets --target-group-arn <arn> --targets Id=i-123 Id=i-456`
- Create listener: `aws elbv2 create-listener --load-balancer-arn <arn> --protocol HTTP --port 80 --default-actions Type=forward,TargetGroupArn=<tg-arn>`
- Describe health: `aws elbv2 describe-target-health --target-group-arn <tg-arn>`

## Console Tips
- Use the "Listeners" tab to set up routing rules (host/path-based for ALB)
- Enable access logs for compliance and troubleshooting
- Attach SSL certificates via ACM for HTTPS
- Monitor health and traffic in the "Monitoring" tab

## Best Practices
- Always enable cross-zone load balancing for even traffic distribution
- Set up health checks to avoid routing to unhealthy targets
- Use security groups and WAF for protection
- Use ALB for HTTP/HTTPS, NLB for TCP/UDP, GWLB for appliances
- Use target groups for flexible backend management
- Enable access logs for auditing

## Troubleshooting
- If targets are unhealthy, check security groups, health check path/port, and instance status
- For SSL issues, verify certificate in ACM and listener configuration
- For uneven traffic, ensure cross-zone load balancing is enabled
- Use CloudWatch metrics for latency, error rates, and traffic analysis

## Practical Tips
- Use ALB for microservices and container workloads (ECS/EKS)
- Use NLB for high-performance, low-latency apps
- Use GWLB for deploying third-party firewalls or appliances
- Rotate SSL certificates regularly

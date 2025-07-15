# AWS Elastic Load Balancing (ELB) – Use Cases

## 1. Web Application High Availability
- **Scenario:** Distribute user traffic across multiple EC2 instances in different AZs for a web app.
- **Best Practice:** Use an Application Load Balancer (ALB) with health checks and cross-zone load balancing enabled.

## 2. Microservices and Containers
- **Scenario:** Route traffic to different microservices or containers based on URL path or hostname.
- **Best Practice:** Use ALB with path-based and host-based routing. Integrate with ECS/EKS for container workloads.

## 3. Real-Time and Low-Latency Applications
- **Scenario:** Support high-throughput, low-latency TCP/UDP workloads (e.g., gaming, financial apps).
- **Best Practice:** Use a Network Load Balancer (NLB) for ultra-high performance and static IP addresses.

## 4. Secure Application Delivery
- **Scenario:** Terminate SSL/TLS at the load balancer and protect apps with WAF.
- **Best Practice:** Use ALB with ACM for SSL certificates and enable AWS WAF for security.

## 5. Hybrid and Legacy Applications
- **Scenario:** Integrate on-premises or legacy apps with cloud-native services.
- **Best Practice:** Use Classic Load Balancer (CLB) for legacy apps, or NLB for hybrid architectures.

## 6. Third-Party Appliance Insertion
- **Scenario:** Deploy and scale virtual appliances (firewalls, IDS/IPS) in the traffic path.
- **Best Practice:** Use Gateway Load Balancer (GWLB) for seamless appliance integration.

## Troubleshooting Tips
- If targets are unhealthy, check health check configuration, security groups, and instance status.
- For SSL issues, verify ACM certificate and listener settings.
- Use access logs and CloudWatch metrics for debugging and compliance.
- Enable cross-zone load balancing for even traffic distribution.

# AWS Elastic Load Balancing (ELB) – Overview

## What is AWS Elastic Load Balancing?
AWS Elastic Load Balancing (ELB) is a fully managed service that automatically distributes incoming application traffic across multiple targets—such as EC2 instances, containers, IP addresses, and Lambda functions—in one or more Availability Zones. ELB helps ensure high availability, fault tolerance, and scalability for your applications.

## Why Use ELB?
- **High Availability:** Distributes traffic across healthy targets in multiple AZs.
- **Fault Tolerance:** Automatically reroutes traffic away from unhealthy targets.
- **Scalability:** Handles sudden traffic spikes by scaling load balancer capacity automatically.
- **Security:** Integrates with AWS Certificate Manager (ACM) for SSL/TLS, supports WAF, and provides DDoS protection via AWS Shield.
- **Simplified Management:** AWS manages the infrastructure, patching, and scaling for you.

## Types of Load Balancers
1. **Application Load Balancer (ALB):** Layer 7 (HTTP/HTTPS), advanced routing, host/path-based routing, WebSocket support, integrates with containers (ECS/EKS).
2. **Network Load Balancer (NLB):** Layer 4 (TCP/UDP), ultra-high performance, static IP, best for extreme performance or low latency.
3. **Gateway Load Balancer (GWLB):** Deploy, scale, and manage third-party virtual appliances (firewalls, etc.).
4. **Classic Load Balancer (CLB):** Legacy, basic Layer 4/7, use only for legacy apps.

## How Does It Work? (Step-by-Step)
1. **Create a Load Balancer:** Choose the type (ALB, NLB, GWLB, or CLB) and configure listeners (protocol/port).
2. **Register Targets:** Add EC2 instances, IPs, Lambda functions, or containers as targets.
3. **Configure Health Checks:** Set up health checks to monitor target health.
4. **Set Up Security:** Attach security groups, configure SSL/TLS, and enable WAF if needed.
5. **Distribute Traffic:** ELB automatically routes incoming requests to healthy targets based on routing rules.
6. **Monitor and Scale:** Use CloudWatch for monitoring, and ELB scales automatically as traffic changes.

## Analogy
Think of ELB as a traffic cop at a busy intersection. When cars (user requests) arrive, the cop directs them to the open lanes (healthy servers). If a lane is closed (server is down), the cop reroutes traffic to the other open lanes, keeping everything moving smoothly.

## Diagram Description
- **Users** send requests to the **Load Balancer** (ALB/NLB/CLB).
- The Load Balancer checks the health of **Targets** (EC2, containers, Lambda, IPs).
- Requests are routed only to healthy targets, distributed across multiple AZs.
- **CloudWatch** monitors traffic, health, and performance.

## Key Features (Expanded)
- **Cross-Zone Load Balancing:** Distributes traffic evenly across all registered targets in all enabled AZs.
- **Sticky Sessions:** ALB/CLB can route a user's requests to the same target (session affinity).
- **SSL/TLS Termination:** Offload SSL decryption to the load balancer.
- **Host/Path-Based Routing:** ALB can route requests based on URL or hostname.
- **WebSocket Support:** ALB supports real-time, bidirectional communication.
- **IP Targeting:** NLB can route to IP addresses, not just EC2.
- **Access Logs:** Store detailed request logs in S3 for analysis.

## Real-World Example
A web application runs on multiple EC2 instances in different AZs. An Application Load Balancer distributes user requests, checks instance health, and automatically reroutes traffic if an instance fails. The app stays available and responsive, even during traffic spikes or outages.

## Advanced/Practical Context
- Use ALB for modern web apps, microservices, and containers (ECS/EKS).
- Use NLB for high-performance, low-latency, or TCP/UDP workloads.
- Integrate with AWS WAF for security and ACM for SSL certificates.
- Use target groups to manage and scale backend resources easily.
- Enable access logs for compliance and troubleshooting.

## Common Pitfalls for Beginners
- Not enabling cross-zone load balancing (can cause uneven traffic).
- Forgetting to set up health checks, leading to traffic sent to unhealthy targets.
- Not configuring security groups or SSL certificates correctly.
- Using Classic Load Balancer for new apps (use ALB/NLB instead).

## Summary
AWS Elastic Load Balancing is essential for building highly available, scalable, and secure applications in the cloud. It automatically distributes traffic, handles failures, and scales with your needs—so your users always get the best experience.

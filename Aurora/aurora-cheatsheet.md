# Aurora Cheatsheet (Beginner to Advanced)

## Creating an Aurora Cluster (Console)
1. Go to the RDS Dashboard in AWS Console.
2. Click "Create database".
3. Select "Amazon Aurora" as the engine.
4. Choose MySQL or PostgreSQL compatibility.
5. Configure cluster settings (name, master user, password).
6. Choose instance class, storage, and Multi-AZ.
7. (Optional) Enable Aurora Serverless.
8. Configure VPC, subnet, and security group.
9. Launch and connect using the cluster endpoint.

## Common CLI Commands
- **List Clusters:** `aws rds describe-db-clusters`
- **Create Cluster:** `aws rds create-db-cluster --db-cluster-identifier my-aurora-cluster --engine aurora-mysql --master-username admin --master-user-password password`
- **Create Instance:** `aws rds create-db-instance --db-instance-identifier my-aurora-instance --db-cluster-identifier my-aurora-cluster --engine aurora-mysql --db-instance-class db.r5.large`
- **Add Replica:** `aws rds create-db-instance --db-instance-identifier my-aurora-replica --db-cluster-identifier my-aurora-cluster --engine aurora-mysql --db-instance-class db.r5.large`
- **Failover Cluster:** `aws rds failover-db-cluster --db-cluster-identifier my-aurora-cluster`
- **Create Global Database:** `aws rds create-global-cluster --global-cluster-identifier my-global-db --source-db-cluster-identifier arn:aws:rds:us-east-1:123456789012:cluster:my-aurora-cluster`

## Important Limits & Defaults
- **Max cluster volume:** 128 TB
- **Max Aurora Replicas:** 15 per cluster
- **Max global secondary regions:** 5
- **Max connections:** Varies by instance size
- **Max failover time:** Typically <30 seconds
- **Max storage IOPS:** Up to 256,000 (Aurora I/O-Optimized)

## Advanced Features
- **Aurora Serverless v2:** Auto-scales compute instantly
- **Global Database:** Multi-region, low-latency reads, disaster recovery
- **Performance Insights:** Advanced monitoring and query tuning
- **Backtrack:** Roll back DB to a previous time (Aurora MySQL only)
- **Zero-downtime patching:** For some maintenance events

## Performance Tuning
- Use Aurora Replicas for read scaling
- Use Performance Insights for query optimization
- Monitor with CloudWatch and Enhanced Monitoring
- Use Global Database for global apps and DR
- Use I/O-Optimized clusters for high-throughput workloads

## When to Use Aurora
- High-performance, highly available relational databases
- Global SaaS, e-commerce, gaming, analytics
- When you need MySQL/PostgreSQL compatibility with better performance

## When NOT to Use Aurora
- For small, low-traffic workloads (RDS or serverless may be cheaper)
- For unsupported MySQL/PostgreSQL features/extensions
- For NoSQL workloads (use DynamoDB)

## Exam Tips
- **Aurora is MySQL/PostgreSQL compatible, but not 100% feature parity**
- **6-way replication across 3 AZs for durability**
- **Aurora Replicas are for scaling and failover**
- **Global Database = multi-region, sub-second replication**
- **Serverless is pay-per-use and auto-scales compute**

## Troubleshooting & Common Errors
- **Cannot connect:** Check security group, subnet, endpoint, and user credentials
- **Failover slow:** Check replica health and cluster configuration
- **Storage full:** Monitor usage and set alerts
- **Unsupported feature:** Check Aurora documentation for compatibility

## Useful Links
- [Aurora User Guide](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/)
- [Aurora Limits](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.Overview.Limits.html)
- [Aurora Best Practices](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.BestPractices.html)

# RDS Cheatsheet (Beginner-Friendly)

## Creating an RDS Instance (Console)
1. Go to the RDS Dashboard in AWS Console.
2. Click "Create database".
3. Choose engine (e.g., MySQL), version, and template (production/dev/test).
4. Set DB instance size, storage, and Multi-AZ if needed.
5. Set master username/password.
6. Choose VPC, subnet, and security group.
7. Configure backups, monitoring, and maintenance.
8. Launch and connect using endpoint, username, and password.

## Common CLI Commands
- **List Instances:** `aws rds describe-db-instances`
- **Create Instance:** `aws rds create-db-instance --db-instance-identifier mydb --db-instance-class db.t3.micro --engine mysql --master-username admin --master-user-password password --allocated-storage 20`
- **Create Snapshot:** `aws rds create-db-snapshot --db-instance-identifier mydb --db-snapshot-identifier mysnap`
- **Restore Snapshot:** `aws rds restore-db-instance-from-db-snapshot --db-instance-identifier mydb2 --db-snapshot-identifier mysnap`
- **Modify Instance:** `aws rds modify-db-instance --db-instance-identifier mydb --allocated-storage 100`

## Important Limits & Defaults
- **DB instances per region:** 40 (soft limit)
- **Read replicas per master:** 5 (MySQL, MariaDB, PostgreSQL)
- **Max storage:** 64 TB (varies by engine)
- **Max connections:** Varies by engine/instance size
- **Max backup retention:** 35 days

## When to Use RDS
- For managed relational databases (web/mobile apps, analytics, business apps)
- When you need high availability (Multi-AZ)
- When you want automated backups and patching

## When NOT to Use RDS
- For NoSQL workloads (use DynamoDB)
- For serverless/ephemeral DBs (use Aurora Serverless)
- For full OS/database customization (use EC2 self-managed DB)

## Exam Tips
- **Multi-AZ = automatic failover, not scaling**
- **Read replicas = scaling reads, not failover (except Aurora)**
- **Backups are deleted with the instance unless you keep snapshots**
- **Encryption must be enabled at creation**
- **IAM authentication is available for MySQL/PostgreSQL**

## Troubleshooting & Common Errors
- **Cannot connect:** Check security group, subnet, and endpoint
- **Slow performance:** Check instance size, storage type, and CloudWatch metrics
- **Backups failing:** Check backup window and storage space
- **Restore failed:** Check snapshot status and engine compatibility

## Useful Links
- [RDS User Guide](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/)
- [RDS Best Practices](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_BestPractices.html)
- [RDS Limits](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Limits.html)

# EFS Cheatsheet (Beginner to Advanced)

## Creating an EFS File System (Console)
1. Go to the EFS Dashboard in AWS Console.
2. Click "Create file system".
3. Choose VPC, subnets, and security groups.
4. (Optional) Enable encryption, set performance and throughput modes.
5. Create the file system.
6. On your EC2 instance, install the NFS client and mount the EFS file system using the DNS name provided.

## Common CLI Commands
- **List File Systems:** `aws efs describe-file-systems`
- **Create File System:** `aws efs create-file-system --creation-token my-efs`
- **Create Mount Target:** `aws efs create-mount-target --file-system-id fs-xxxx --subnet-id subnet-xxxx --security-groups sg-xxxx`
- **Describe Mount Targets:** `aws efs describe-mount-targets --file-system-id fs-xxxx`
- **Delete File System:** `aws efs delete-file-system --file-system-id fs-xxxx`

## Important Limits & Defaults
- **Max file system size:** Virtually unlimited (scales automatically)
- **Max throughput (burst mode):** Scales with storage size
- **Max throughput (provisioned):** Up to 1 GiB/s
- **Max files per file system:** Millions (limited by storage)
- **Max mount targets:** 1 per AZ
- **Max access points:** 120 per file system

## Advanced Features
- **Lifecycle management:** Move files to Infrequent Access (IA) storage class
- **Access Points:** Fine-grained access control for apps/users
- **Automatic backups:** Daily backups with AWS Backup
- **Encryption:** At rest (KMS) and in transit (TLS)
- **CloudWatch monitoring:** Throughput, IOPS, burst credits

## Performance Tuning
- Use General Purpose mode for most workloads
- Use Max I/O for highly parallel, high-throughput workloads
- Use Provisioned Throughput for consistent performance
- Monitor burst credits and throughput with CloudWatch
- Distribute clients across AZs for high availability

## When to Use EFS
- Shared storage for Linux EC2, containers, Lambda
- Web server farms, analytics, home directories
- When you need POSIX-compliant, elastic file storage

## When NOT to Use EFS
- For Windows workloads (use FSx for Windows)
- For block storage (use EBS)
- For object storage (use S3)

## Exam Tips
- **EFS is NFS only (Linux/Unix)**
- **Performance depends on file system size in burst mode**
- **Mount targets must be in each AZ for HA**
- **Lifecycle management moves files to IA for cost savings**
- **Access Points enable fine-grained access control**

## Troubleshooting & Common Errors
- **Cannot mount:** Check security group, subnet, NFS client, and DNS name
- **Slow performance:** Check throughput mode, burst credits, and file system size
- **Access denied:** Check IAM, security group, and access point permissions
- **Mount target missing:** Create a mount target in each AZ

## Useful Links
- [EFS User Guide](https://docs.aws.amazon.com/efs/latest/ug/)
- [EFS Limits](https://docs.aws.amazon.com/efs/latest/ug/limits.html)
- [EFS Best Practices](https://docs.aws.amazon.com/efs/latest/ug/best-practices.html)

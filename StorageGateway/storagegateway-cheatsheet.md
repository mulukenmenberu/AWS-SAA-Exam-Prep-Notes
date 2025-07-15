# Storage Gateway Cheatsheet (Beginner to Advanced)

## Deploying a File Gateway (Console)
1. Download and deploy the Storage Gateway VM on-premises
2. Activate the gateway in the AWS Console
3. Configure local disks for cache and upload buffer
4. Create a file share (NFS/SMB) and map to an S3 bucket
5. Mount the file share on your on-premises servers
6. Monitor usage and performance in the AWS Console

## Common CLI Commands
- **List Gateways:** `aws storagegateway list-gateways`
- **Create Gateway:** `aws storagegateway create-gateway --gateway-type FILE_S3 --gateway-name my-gateway --gateway-region us-east-1 --gateway-ip-address 10.0.0.10`
- **Create File Share:** `aws storagegateway create-nfs-file-share --gateway-arn arn:aws:storagegateway:... --role arn:aws:iam::...:role/... --location-arn arn:aws:s3:::my-bucket`
- **List File Shares:** `aws storagegateway list-file-shares`
- **Create Volume:** `aws storagegateway create-cached-iscsi-volume ...`
- **Create Tape:** `aws storagegateway create-tapes ...`
- **Delete Gateway:** `aws storagegateway delete-gateway --gateway-arn arn:aws:storagegateway:...`

## Important Limits & Defaults
- **Max file shares per gateway:** 50
- **Max file size:** 5 TB (File Gateway)
- **Max volumes per gateway:** 32 (Volume Gateway)
- **Max tapes per gateway:** 1,500 (Tape Gateway)
- **Max cache size:** 64 TB (File Gateway)
- **Max upload buffer:** 2 TB (File Gateway)
- **Max gateways per region:** 50 (soft limit)

## Advanced Features
- **S3 Object Lock:** For compliance and WORM storage
- **Lifecycle policies:** Move data to Glacier for cost savings
- **Access control:** IAM, SMB ACLs, VPC endpoints
- **Automatic backups:** EBS snapshots, S3 versioning
- **CloudWatch monitoring:** Cache hit ratio, throughput, latency

## When to Use Storage Gateway
- Hybrid cloud storage, backup, and DR
- Cloud backup for file servers, VTL replacement
- Seamless integration with S3, Glacier, EBS

## When NOT to Use Storage Gateway
- For high-performance, low-latency primary storage (use EFS/FSx)
- For full NAS replacement (File Gateway has limitations)
- For workloads not requiring hybrid cloud

## Exam Tips
- **File Gateway = NFS/SMB to S3, local cache**
- **Volume Gateway = iSCSI block storage, EBS snapshots**
- **Tape Gateway = VTL, S3/Glacier for backup/archive**
- **Cache size impacts performance**
- **Network config and bandwidth are critical**

## Troubleshooting & Common Errors
- **Slow uploads:** Check cache size, network bandwidth, and buffer configuration
- **Access denied:** Check IAM, SMB/NFS permissions, and S3 bucket policy
- **Gateway offline:** Check VM status, network, and AWS Console
- **File not visible in S3:** Check upload buffer and sync status

## Useful Links
- [Storage Gateway User Guide](https://docs.aws.amazon.com/storagegateway/latest/userguide/)
- [Storage Gateway Limits](https://docs.aws.amazon.com/storagegateway/latest/userguide/limits.html)
- [Best Practices](https://docs.aws.amazon.com/storagegateway/latest/userguide/best-practices.html)

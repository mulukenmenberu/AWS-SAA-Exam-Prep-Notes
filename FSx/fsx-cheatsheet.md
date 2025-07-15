# FSx Cheatsheet (Beginner to Advanced)

## Creating an FSx File System (Console)
1. Go to the FSx Dashboard in AWS Console.
2. Click "Create file system".
3. Choose the file system type (Windows, Lustre, ONTAP, OpenZFS).
4. Configure storage, throughput, and network settings.
5. (Optional) Set up AD integration, S3 data repository, or advanced features.
6. Launch and mount from EC2 or on-premises clients.

## Common CLI Commands
- **List File Systems:** `aws fsx describe-file-systems`
- **Create FSx for Windows:** `aws fsx create-file-system --file-system-type WINDOWS --storage-capacity 300 --subnet-ids subnet-xxxx --windows-configuration ...`
- **Create FSx for Lustre:** `aws fsx create-file-system --file-system-type LUSTRE --storage-capacity 1200 --subnet-ids subnet-xxxx --lustre-configuration ...`
- **Create FSx for ONTAP:** `aws fsx create-file-system --file-system-type ONTAP --storage-capacity 1024 --subnet-ids subnet-xxxx --ontap-configuration ...`
- **Create FSx for OpenZFS:** `aws fsx create-file-system --file-system-type OPENZFS --storage-capacity 1024 --subnet-ids subnet-xxxx --openzfs-configuration ...`
- **Delete File System:** `aws fsx delete-file-system --file-system-id fs-xxxx`

## Important Limits & Defaults
- **FSx for Windows:** 32 TB per file system, up to 80,000 IOPS, 2 GB/s throughput
- **FSx for Lustre:** 100s of GB/s throughput, millions of IOPS, up to 512 TB per file system
- **FSx for ONTAP:** 192 TB per file system, 24 TB per volume, multi-protocol
- **FSx for OpenZFS:** 512 TB per file system, 1 GB/s throughput per file server
- **Max file systems per region:** 100 (soft limit)

## Advanced Features
- **Multi-AZ deployment:** For high availability (Windows, ONTAP)
- **S3 integration:** For Lustre and ONTAP (data import/export, tiering)
- **Snapshots and clones:** For ONTAP and OpenZFS
- **Active Directory integration:** For Windows and ONTAP
- **Data deduplication, compression, tiering:** For cost and performance optimization

## Performance Tuning
- Choose the right FSx type for your workload
- Use multi-AZ for HA and DR
- Monitor with CloudWatch for throughput, IOPS, and health
- Use S3 tiering for cost savings (Lustre, ONTAP)
- Use snapshots for backup and fast recovery

## When to Use FSx
- Windows file shares (FSx for Windows)
- HPC, ML, analytics (FSx for Lustre)
- Enterprise NAS, multi-protocol, DR (FSx for ONTAP)
- Linux app data, DevOps, analytics (FSx for OpenZFS)

## When NOT to Use FSx
- For simple object storage (use S3)
- For Linux shared storage (use EFS unless you need advanced features)
- For workloads not requiring high performance or advanced features

## Exam Tips
- **FSx for Windows = SMB, AD integration, Windows ACLs**
- **FSx for Lustre = HPC, S3 integration, parallel I/O**
- **FSx for ONTAP = multi-protocol, snapshots, S3 tiering**
- **FSx for OpenZFS = Linux, NFS, snapshots, clones**
- **Network config (VPC, security groups) is critical for access**

## Troubleshooting & Common Errors
- **Cannot mount:** Check network, security group, protocol, and client compatibility
- **Slow performance:** Check throughput, IOPS, and file system type
- **Access denied:** Check AD, IAM, and file system permissions
- **S3 integration not working:** Check S3 bucket policy and FSx config

## Useful Links
- [FSx User Guide](https://docs.aws.amazon.com/fsx/latest/UserGuide/)
- [FSx Limits](https://docs.aws.amazon.com/fsx/latest/WindowsGuide/limits.html)
- [FSx Best Practices](https://docs.aws.amazon.com/fsx/latest/WindowsGuide/best-practices.html)

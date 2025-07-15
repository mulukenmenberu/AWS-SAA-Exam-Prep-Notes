# Amazon FSx – Cheatsheet

## Key Facts
- **File System Types:** Windows, Lustre, NetApp ONTAP, OpenZFS
- **Protocols:** SMB, NFS, Lustre, ZFS
- **Fully Managed:** AWS handles provisioning, patching, scaling, backups
- **Performance:** High throughput, low latency
- **Multi-AZ:** High availability and failover support
- **Backups/Snapshots:** Automated and on-demand
- **Data Tiering:** Move cold data to lower-cost storage
- **Hybrid Support:** Connect on-premises via Direct Connect/VPN
- **Security:** Encryption at rest/in transit, IAM, AD, VPC

## Common CLI Commands
- List file systems: `aws fsx describe-file-systems`
- Create FSx for Windows: `aws fsx create-file-system --file-system-type WINDOWS ...`
- Create FSx for Lustre: `aws fsx create-file-system --file-system-type LUSTRE ...`
- Create FSx for ONTAP: `aws fsx create-file-system --file-system-type ONTAP ...`
- Create FSx for OpenZFS: `aws fsx create-file-system --file-system-type OPENZFS ...`
- Delete file system: `aws fsx delete-file-system --file-system-id fs-123`
- List backups: `aws fsx describe-backups`

## Console Tips
- Use the wizard to select the right FSx type for your workload
- Enable multi-AZ for high availability (where supported)
- Set up automatic backups and snapshots
- Monitor performance in the "Monitoring" tab
- Use access logs for auditing and troubleshooting

## Best Practices
- Choose the FSx type that matches your workload (Windows, Lustre, ONTAP, OpenZFS)
- Configure security groups, VPC, and AD integration as needed
- Enable backups and monitor usage/costs
- Use data tiering to optimize storage costs
- Integrate with AWS Backup for centralized management

## Troubleshooting
- If you can't connect, check network settings, security groups, and protocol support
- For performance issues, adjust throughput/IOPS or review CloudWatch metrics
- For backup/restore issues, check backup status and permissions
- Use AWS Support and documentation for advanced troubleshooting

## Practical Tips
- Use FSx for Lustre with S3 for fast, parallel data processing
- Use FSx for NetApp ONTAP for enterprise NAS features
- Use FSx for OpenZFS for open-source, cost-effective storage
- Rotate credentials and review access logs regularly

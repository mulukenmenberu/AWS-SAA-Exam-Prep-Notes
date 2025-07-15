# S3 Cheatsheet (Beginner-Friendly)

## Creating a Bucket (Console)
1. Go to the S3 Dashboard in AWS Console.
2. Click "Create bucket".
3. Enter a unique bucket name and select a region.
4. Leave "Block all public access" checked (recommended for most use cases).
5. Click "Create bucket".

## Uploading Files (Console)
1. Click your bucket name.
2. Click "Upload".
3. Drag and drop files or select them.
4. Set storage class, encryption, and permissions as needed.
5. Click "Upload".

## Common CLI Commands
- **List Buckets:** `aws s3 ls`
- **Create Bucket:** `aws s3 mb s3://my-bucket`
- **Upload File:** `aws s3 cp file.txt s3://my-bucket/`
- **Sync Directory:** `aws s3 sync . s3://my-bucket/`
- **Enable Versioning:** `aws s3api put-bucket-versioning --bucket my-bucket --versioning-configuration Status=Enabled`
- **Set Lifecycle Policy:** `aws s3api put-bucket-lifecycle-configuration --bucket my-bucket --lifecycle-configuration file://lifecycle.json`

## Important Limits & Defaults
- **Buckets per account:** 100 (soft limit)
- **Objects per bucket:** Unlimited
- **Object size:** Up to 5TB (single PUT up to 5GB, use multipart for larger)
- **Max key length:** 1,024 bytes
- **Max bucket name length:** 63 characters

## When to Use S3
- Store static files (images, videos, backups, logs)
- Host static websites
- Data lakes and analytics
- Disaster recovery and archiving

## When NOT to Use S3
- For block storage (use EBS)
- For file systems with POSIX requirements (use EFS/FSx)
- For high-transaction databases (use RDS, DynamoDB)

## Exam Tips
- **Buckets are globally unique**
- **Versioning must be enabled before use**
- **Lifecycle policies automate storage class transitions and deletions**
- **Block Public Access is enabled by default**
- **S3 is eventually consistent for overwrite PUTs and DELETEs**

## Troubleshooting & Common Errors
- **Access Denied:** Check bucket policy, IAM permissions, and Block Public Access settings
- **Bucket name already exists:** Choose a unique name
- **Slow upload/download:** Use multipart upload for large files
- **Object not found:** Check key name and versioning

## Useful Links
- [S3 User Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/)
- [S3 Storage Classes](https://aws.amazon.com/s3/storage-classes/)
- [S3 Pricing](https://aws.amazon.com/s3/pricing/)

# AWS DynamoDB – Cheatsheet

## Key Facts
- **NoSQL Database:** Key-value and document data model
- **Serverless:** No infrastructure to manage
- **Single-digit ms Latency:** Fast at any scale
- **Capacity Modes:** On-Demand (auto-scales) or Provisioned (set RCU/WCU)
- **Indexes:** Global Secondary Index (GSI), Local Secondary Index (LSI)
- **Streams:** Capture table changes for event-driven apps
- **Transactions:** ACID-compliant multi-item, multi-table
- **DAX:** In-memory cache for microsecond reads
- **Global Tables:** Multi-region, active-active replication
- **Encryption:** At rest and in transit

## Common CLI Commands
- List tables: `aws dynamodb list-tables`
- Create table: `aws dynamodb create-table --table-name MyTable --attribute-definitions ... --key-schema ... --billing-mode PAY_PER_REQUEST`
- Put item: `aws dynamodb put-item --table-name MyTable --item '{"id": {"S": "123"}, "name": {"S": "Alice"}}'`
- Get item: `aws dynamodb get-item --table-name MyTable --key '{"id": {"S": "123"}}'`
- Query: `aws dynamodb query --table-name MyTable --key-condition-expression 'id = :id' --expression-attribute-values '{":id": {"S": "123"}}'`
- Scan: `aws dynamodb scan --table-name MyTable`
- Update table: `aws dynamodb update-table --table-name MyTable --provisioned-throughput ReadCapacityUnits=5,WriteCapacityUnits=5`

## Console Tips
- Use "Create Table" wizard for step-by-step setup
- Enable point-in-time recovery for backups
- Use "Explore Table" to view and edit data
- Monitor metrics in the "Capacity" and "Alarms" tabs

## Best Practices
- Design primary key for your access patterns (avoid hot partitions)
- Use queries instead of scans for efficiency
- Use GSIs/LSIs for flexible querying
- Enable auto scaling or use On-Demand for unpredictable workloads
- Monitor consumed capacity and set CloudWatch alarms
- Use DAX for read-heavy, low-latency workloads
- Enable TTL for automatic item expiration

## Troubleshooting
- Throttling? Check consumed vs. provisioned capacity, hot partitions, or switch to On-Demand
- Missing data? Check key schema and attribute types
- Slow queries? Use indexes and avoid scans
- Backup/restore issues? Ensure point-in-time recovery is enabled

## Practical Tips
- Use DynamoDB Streams + Lambda for real-time triggers
- Use IAM policies for fine-grained access control
- Use VPC endpoints for private connectivity
- Use AWS SDKs for batch operations and pagination

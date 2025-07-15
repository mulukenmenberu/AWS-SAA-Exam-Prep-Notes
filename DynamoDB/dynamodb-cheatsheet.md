# DynamoDB Cheatsheet (Beginner to Advanced)

## Creating a Table (Console)
1. Go to DynamoDB Dashboard in AWS Console.
2. Click "Create table".
3. Enter table name, partition key (and sort key if needed).
4. Choose capacity mode (On-Demand or Provisioned).
5. (Optional) Add indexes, enable streams, TTL, encryption.
6. Create table and start adding items.

## Common CLI Commands
- **List Tables:** `aws dynamodb list-tables`
- **Create Table:** `aws dynamodb create-table --table-name MyTable --attribute-definitions AttributeName=UserID,AttributeType=S --key-schema AttributeName=UserID,KeyType=HASH --billing-mode PAY_PER_REQUEST`
- **Put Item:** `aws dynamodb put-item --table-name MyTable --item '{"UserID": {"S": "123"}, "Name": {"S": "Alice"}}'`
- **Get Item:** `aws dynamodb get-item --table-name MyTable --key '{"UserID": {"S": "123"}}'`
- **Query:** `aws dynamodb query --table-name MyTable --key-condition-expression "UserID = :uid" --expression-attribute-values '{":uid": {"S": "123"}}'`
- **Update Table (add GSI):** `aws dynamodb update-table --table-name MyTable --attribute-definitions AttributeName=Email,AttributeType=S --global-secondary-index-updates '[{"Create":{"IndexName":"EmailIndex","KeySchema":[{"AttributeName":"Email","KeyType":"HASH"}],"Projection":{"ProjectionType":"ALL"},"ProvisionedThroughput":{"ReadCapacityUnits":5,"WriteCapacityUnits":5}}}]'`

## Important Limits & Defaults
- **Max item size:** 400 KB
- **Max tables per region:** 256 (soft limit)
- **Max GSIs per table:** 20
- **Max LSIs per table:** 5 (at creation only)
- **Max partition key size:** 2048 bytes
- **Max sort key size:** 1024 bytes
- **Max attribute name/value size:** 65535 bytes
- **Max batch write:** 25 items per request

## Advanced Features
- **DAX:** In-memory cache for microsecond reads
- **Streams:** Real-time change data capture
- **Transactions:** ACID operations across multiple items/tables
- **Global Tables:** Multi-region, active-active replication
- **TTL:** Automatic item expiration
- **Point-in-Time Recovery:** Restore to any second in the last 35 days

## Performance Tuning
- Use high-cardinality partition keys to avoid hot partitions
- Use On-Demand for unpredictable workloads, Provisioned for cost control
- Use DAX for read-heavy, low-latency workloads
- Monitor throttling and latency with CloudWatch
- Use BatchWrite/BatchGet for bulk operations

## When to Use DynamoDB
- Serverless, scalable NoSQL workloads
- High-velocity data (IoT, gaming, mobile, analytics)
- Event-driven architectures (with Streams + Lambda)

## When NOT to Use DynamoDB
- Complex queries, joins, or multi-table transactions (use RDS/Aurora)
- Large item sizes (>400 KB)
- Strict relational data models

## Exam Tips
- **Partition key design is critical for performance**
- **On-Demand mode is best for unpredictable workloads**
- **Streams enable event-driven processing**
- **DAX is for microsecond read latency**
- **Transactions are ACID but have limits (max 25 items/4 MB per transaction)**

## Troubleshooting & Common Errors
- **Throttling (Provisioned mode):** Increase capacity, use Auto Scaling, or switch to On-Demand
- **Hot partitions:** Redesign partition key
- **ValidationException:** Check attribute types and sizes
- **ResourceNotFoundException:** Table or index does not exist
- **ConditionalCheckFailedException:** Condition in write failed

## Useful Links
- [DynamoDB User Guide](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/)
- [DynamoDB Limits](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Limits.html)
- [Best Practices](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/best-practices.html)

# Kinesis Cheatsheet (Beginner to Advanced)

## Creating a Data Stream (Console)
1. Go to the Kinesis Dashboard in AWS Console
2. Click "Create data stream"
3. Enter stream name and number of shards
4. Configure retention, encryption, and monitoring
5. Create the stream and note the ARN

## Common CLI Commands
- **List Streams:** `aws kinesis list-streams`
- **Create Stream:** `aws kinesis create-stream --stream-name MyStream --shard-count 2`
- **Put Record:** `aws kinesis put-record --stream-name MyStream --partition-key key1 --data "SGVsbG8="`
- **Get Records:** `aws kinesis get-records --shard-iterator <iterator>`
- **Describe Stream:** `aws kinesis describe-stream --stream-name MyStream`
- **Split Shard:** `aws kinesis split-shard --stream-name MyStream --shard-to-split shardId-000000000000 --new-starting-hash-key 340282366920938463463374607431768211456`
- **Merge Shards:** `aws kinesis merge-shards --stream-name MyStream --shard-to-merge shardId-000000000000 --adjacent-shard-to-merge shardId-000000000001`

## Firehose CLI Examples
- **List Delivery Streams:** `aws firehose list-delivery-streams`
- **Create Delivery Stream:** `aws firehose create-delivery-stream --delivery-stream-name MyFirehose --s3-destination-configuration ...`
- **Put Record:** `aws firehose put-record --delivery-stream-name MyFirehose --record Data="SGVsbG8="`

## Important Limits & Defaults
- **KDS max shards per stream:** 500 (soft limit)
- **KDS record size:** 1 MB
- **KDS max records per second per shard:** 1,000
- **KDS retention:** 24h (default), up to 7d
- **Firehose buffer size:** 1–128 MB (S3), 1–1000 records (default 5 min)
- **Firehose max delivery streams:** 50 (soft limit)
- **Analytics max input streams:** 5 per application

## Advanced Features
- **Enhanced fan-out:** Dedicated throughput per consumer (KDS)
- **Data transformation:** Use Lambda with Firehose
- **Scaling:** Split/merge shards in KDS
- **Server-side encryption:** KMS integration
- **VPC endpoints:** Private connectivity
- **Video Streams:** Real-time video ingestion and playback

## Performance Tuning
- Monitor shard metrics and scale as needed
- Use partition keys to distribute load evenly
- Use enhanced fan-out for high-throughput consumers
- Use Firehose for easy delivery to S3/Redshift/OpenSearch
- Tune Firehose buffer size for latency vs. cost

## When to Use Kinesis
- Real-time analytics, log processing, IoT, clickstreams
- Streaming data to S3, Redshift, OpenSearch, or custom endpoints
- Video ingestion and analytics

## When NOT to Use Kinesis
- For simple pub/sub (use SNS/SQS)
- For batch ETL (use Glue, Data Pipeline)
- For very large files (use S3 directly)

## Exam Tips
- **KDS = real-time, sharded, scalable, 24h–7d retention**
- **Firehose = easy delivery, no shard management, near real-time**
- **Analytics = SQL on streaming data**
- **Enhanced fan-out = dedicated throughput per consumer**
- **Scaling KDS requires resharding**

## Troubleshooting & Common Errors
- **ProvisionedThroughputExceeded:** Add shards or reduce write rate
- **Data loss:** Increase retention or read more frequently
- **Firehose delivery failures:** Check destination permissions and buffer settings
- **Access denied:** Check IAM policies
- **High latency:** Tune buffer size, shard count, and consumer logic

## Useful Links
- [Kinesis User Guide](https://docs.aws.amazon.com/streams/latest/dev/introduction.html)
- [Kinesis Limits](https://docs.aws.amazon.com/streams/latest/dev/service-sizes-and-limits.html)
- [Best Practices](https://docs.aws.amazon.com/streams/latest/dev/best-practices.html)

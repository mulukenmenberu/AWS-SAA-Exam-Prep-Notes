# AWS Migration & Transfer – Cheatsheet

## Key Facts
- **DMS:** Migrate databases with minimal downtime
- **MGN/SMS:** Lift-and-shift server migration
- **DataSync:** Automated, scheduled data transfer
- **Snowball/Snowmobile:** Physical devices for large-scale data transfer
- **Storage Gateway:** Hybrid storage integration

## Common CLI Commands
- List DMS tasks: `aws dms describe-replication-tasks`
- Start DMS task: `aws dms start-replication-task ...`
- List DataSync tasks: `aws datasync list-tasks`
- Start DataSync task: `aws datasync start-task-execution --task-arn <arn>`

## Console Tips
- Use Migration Hub to track all migrations
- Monitor DMS task status and logs for errors
- Use DataSync scheduling for recurring transfers
- Track Snowball jobs in the Snow Family console

## Best Practices
- Test migrations in a non-production environment first
- Use continuous replication for minimal downtime
- Validate data integrity after migration
- Encrypt data in transit and at rest

## Troubleshooting
- Check CloudWatch logs for migration errors
- Monitor task progress in Migration Hub
- Use DMS validation features to ensure data consistency

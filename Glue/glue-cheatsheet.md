# AWS Glue – Cheatsheet

## Key Facts
- **Serverless ETL:** No servers to manage, pay-per-use
- **Data Catalog:** Central metadata repository
- **Crawlers:** Auto-discover and catalog data
- **Job Types:** ETL (Python/Scala), streaming, visual (Glue Studio)
- **Integration:** Works with S3, Redshift, Athena, Lake Formation

## Common CLI Commands
- List jobs: `aws glue list-jobs`
- Start job: `aws glue start-job-run --job-name <name>`
- List crawlers: `aws glue list-crawlers`
- Start crawler: `aws glue start-crawler --name <name>`
- Get catalog tables: `aws glue get-tables --database-name <db>`

## Console Tips
- Use Glue Studio for visual job authoring
- Schedule jobs and crawlers with triggers
- Monitor job runs and logs in the console

## Best Practices
- Partition data for performance
- Use Glue Data Catalog as the single source of truth
- Monitor job metrics and tune worker types
- Use version control for ETL scripts

## Troubleshooting
- Check CloudWatch logs for job errors
- Monitor job metrics for performance bottlenecks
- Validate schema changes with crawlers before production

# AWS Migration & Transfer – Overview

## What are AWS Migration & Transfer Services?
AWS offers a suite of services to help organizations move data, applications, and workloads from on-premises environments or other clouds to AWS. These services support a variety of migration and transfer scenarios, from databases to large-scale data sets and live applications.

## Key Services
- **AWS Database Migration Service (DMS):** Migrate databases to AWS with minimal downtime.
- **AWS Application Migration Service (MGN):** Lift-and-shift server migration.
- **AWS Server Migration Service (SMS):** Agentless migration of on-premises VMs.
- **AWS DataSync:** Automated, accelerated data transfer between on-premises and AWS.
- **AWS Snow Family (Snowball, Snowmobile):** Physical devices for petabyte-scale data transfer.
- **AWS Storage Gateway:** Hybrid cloud storage integration.

## Key Features
- **Automated Migration:** Orchestrate and track migrations with Migration Hub.
- **Minimal Downtime:** Continuous replication for near-zero downtime migrations.
- **Hybrid Integration:** Seamless data movement between on-premises and AWS.
- **Security & Compliance:** Encryption in transit and at rest, audit logging.

## Architecture
- **Migration Hub:** Central dashboard for tracking migrations.
- **DMS:** Source and target endpoints, replication instance, continuous data replication.
- **Snow Family:** Physical device shipped to customer, data loaded and shipped to AWS.

## Advanced/Practical Context
- Use DMS for heterogeneous (e.g., Oracle to Aurora) and homogeneous (e.g., MySQL to RDS MySQL) migrations.
- Use DataSync for recurring or scheduled data transfers.
- Use Snowball for initial bulk transfer, then DataSync for ongoing sync.

## Real-World Relevance
- Used by enterprises for cloud adoption, disaster recovery, and hybrid cloud strategies.
- Essential for large-scale migrations, compliance-driven industries, and data center exits.

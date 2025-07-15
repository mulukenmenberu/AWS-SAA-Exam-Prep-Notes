# AWS DynamoDB – Use Cases

## 1. User Profile Store
- **Scenario:** Store and retrieve user profiles for a web or mobile app.
- **Best Practice:** Use a partition key like `UserID` for fast lookups. Use GSIs for querying by email or username.

## 2. Session Management
- **Scenario:** Manage user sessions and authentication tokens for millions of users.
- **Best Practice:** Use TTL to automatically expire old sessions. Use On-Demand mode for unpredictable traffic.

## 3. Real-Time Leaderboards
- **Scenario:** Track and display high scores in a gaming app.
- **Best Practice:** Use a composite key (e.g., `GameID` as partition key, `Score` as sort key). Use LSIs for alternate sorting (e.g., by timestamp).

## 4. IoT Device Data Ingestion
- **Scenario:** Store time-series data from thousands of IoT devices.
- **Best Practice:** Use a composite key (`DeviceID` + `Timestamp`). Use Streams + Lambda for real-time analytics or alerts.

## 5. Shopping Cart and Order Management
- **Scenario:** Store shopping cart items and order history for e-commerce apps.
- **Best Practice:** Use a partition key for `UserID` and a sort key for `OrderID` or `Timestamp`. Use transactions for order processing.

## 6. Event-Driven Architectures
- **Scenario:** Trigger workflows or analytics when data changes.
- **Best Practice:** Enable DynamoDB Streams and connect to Lambda for real-time processing.

## Troubleshooting Tips
- If you see throttling, check for hot partitions or increase capacity.
- Use CloudWatch metrics to monitor read/write usage and set alarms.
- Use GSIs for flexible queries, but monitor write costs.
- Use point-in-time recovery for backup and restore.

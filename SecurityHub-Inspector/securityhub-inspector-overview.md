# AWS Security Hub & Inspector – Overview

## What is AWS Security Hub?
AWS Security Hub is a cloud security posture management service that aggregates, organizes, and prioritizes security findings from AWS services (like GuardDuty, Macie, Inspector) and third-party tools. It provides a comprehensive view of your security state and compliance status across AWS accounts.

## What is AWS Inspector?
Amazon Inspector is an automated vulnerability management service that scans AWS workloads (EC2, Lambda, ECR) for software vulnerabilities and unintended network exposure. It provides continuous assessment and actionable findings.

## Key Features
- **Centralized Security Findings:** Aggregates findings from multiple AWS and third-party sources.
- **Automated Compliance Checks:** Monitors resources against standards (CIS, PCI DSS, etc.).
- **Vulnerability Scanning:** Inspector scans for CVEs, missing patches, and network risks.
- **Integration:** Works with AWS Organizations for multi-account visibility.
- **Automated Remediation:** Integrates with Lambda and Systems Manager for response.
- **Dashboards & Insights:** Visualize security posture and trends.

## Architecture
- **Security Hub:** Central console, integrates with AWS services and third-party tools, supports cross-account aggregation.
- **Inspector:** Agentless (for Lambda/ECR), lightweight agent (for EC2), continuous scanning.

## Advanced/Practical Context
- Use Security Hub as the single pane of glass for all security findings.
- Automate remediation with Lambda and SSM Automation.
- Integrate with SIEM/SOAR tools for enterprise workflows.

## Real-World Relevance
- Used by security teams to monitor, prioritize, and remediate risks across AWS environments.
- Essential for regulated industries and organizations with complex, multi-account AWS setups.

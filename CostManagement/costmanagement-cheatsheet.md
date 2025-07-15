# AWS Cost Management – Cheatsheet

## Key Facts
- **Cost Explorer:** Visualize and analyze costs
- **Budgets:** Set and track spending limits
- **CUR:** Detailed billing and usage data
- **Savings Plans/RIs:** Commit for discounts
- **Tags:** Allocate costs by project/team

## Common CLI Commands
- Get cost and usage: `aws ce get-cost-and-usage --time-period Start=<>,End=<> --granularity MONTHLY --metrics BlendedCost`
- List budgets: `aws budgets describe-budgets --account-id <id>`
- Create budget: `aws budgets create-budget ...`

## Console Tips
- Use Cost Explorer for trend analysis
- Set up budget alerts for cost overruns
- Enable cost allocation tags in Billing console

## Best Practices
- Tag all resources for cost allocation
- Review recommendations for savings
- Use budgets and alerts to control spending
- Regularly review unused resources

## Troubleshooting
- Check for missing tags in cost allocation
- Review CUR for unexpected charges
- Use support center for billing disputes

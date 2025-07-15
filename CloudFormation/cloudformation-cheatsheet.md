# AWS CloudFormation – Cheatsheet

## Key Facts
- **Infrastructure as Code (IaC):** Define AWS resources in YAML or JSON templates.
- **Stacks:** Group of resources managed together.
- **StackSets:** Deploy stacks across multiple accounts/regions.
- **Change Sets:** Preview changes before applying them.
- **Drift Detection:** Detects manual changes outside CloudFormation.
- **Parameters/Outputs:** Make templates reusable and share values between stacks.
- **Nested Stacks:** Modularize complex templates.

## Common CLI Commands
- Validate template: `aws cloudformation validate-template --template-body file://template.yaml`
- Create stack: `aws cloudformation create-stack --stack-name my-stack --template-body file://template.yaml --parameters ParameterKey=Env,ParameterValue=dev`
- Update stack: `aws cloudformation update-stack --stack-name my-stack --template-body file://template.yaml`
- Delete stack: `aws cloudformation delete-stack --stack-name my-stack`
- List stacks: `aws cloudformation list-stacks`
- Describe stack events: `aws cloudformation describe-stack-events --stack-name my-stack`
- Detect drift: `aws cloudformation detect-stack-drift --stack-name my-stack`

## Console Tips
- Use the "Designer" for visual template editing.
- Always check the "Events" tab for stack progress and errors.
- Use change sets to preview updates before applying.
- Enable termination protection to prevent accidental stack deletion.

## Best Practices
- Use parameters and mappings for flexible, reusable templates.
- Modularize with nested stacks for large projects.
- Store templates in version control (Git).
- Use outputs to share values (e.g., VPC ID) between stacks.
- Tag resources for cost allocation and management.
- Always validate templates before deploying.

## Troubleshooting
- Check stack events for error messages and failed resources.
- Use rollback triggers to automatically revert on failure.
- Use drift detection to find manual changes outside CloudFormation.
- If a stack fails, review the "Resources" and "Events" tabs for details.
- Remember: Deleting a stack deletes all its resources!

## Practical Tips
- Start with AWS sample templates for common architectures.
- Use the "!Ref" and "!GetAtt" functions to reference resources and attributes.
- Use the "DependsOn" attribute to control resource creation order.
- For sensitive data, use the "NoEcho" property for parameters.

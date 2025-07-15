# VPC Cheatsheet (Beginner-Friendly)

## Creating a VPC (Console)
1. Go to the VPC Dashboard in AWS Console.
2. Click "Create VPC".
3. Enter a name and CIDR block (e.g., 10.0.0.0/16).
4. Add subnets in different AZs (for high availability).
5. Attach an Internet Gateway.
6. Create route tables and associate with subnets.
7. Set up security groups and NACLs.

## Common CLI Commands
- **Create VPC:** `aws ec2 create-vpc --cidr-block 10.0.0.0/16`
- **Create Subnet:** `aws ec2 create-subnet --vpc-id vpc-xxxx --cidr-block 10.0.1.0/24`
- **Create IGW:** `aws ec2 create-internet-gateway`
- **Attach IGW:** `aws ec2 attach-internet-gateway --vpc-id vpc-xxxx --internet-gateway-id igw-xxxx`
- **Create Route Table:** `aws ec2 create-route-table --vpc-id vpc-xxxx`
- **Associate Route Table:** `aws ec2 associate-route-table --subnet-id subnet-xxxx --route-table-id rtb-xxxx`
- **Create Security Group:** `aws ec2 create-security-group --group-name my-sg --description "desc" --vpc-id vpc-xxxx`

## Important Limits & Defaults
- **VPCs per region:** 5 (soft limit)
- **Subnets per VPC:** 200
- **Route tables per VPC:** 50
- **IGWs per region:** 5
- **Security groups per VPC:** 250
- **NACLs per VPC:** 200

## When to Use VPC
- For any AWS resource that needs network isolation or custom networking
- For secure, multi-tier applications
- For hybrid cloud (connect to on-premises)

## When NOT to Use VPC
- For simple, public-only workloads (default VPC is fine for quick tests)
- For serverless-only architectures (but VPC can still be used for Lambda networking)

## Exam Tips
- **Security Groups are stateful, NACLs are stateless**
- **Public subnet = route to IGW**
- **Private subnet = no direct route to IGW**
- **NAT Gateway allows outbound internet from private subnet**
- **Overlapping CIDR blocks prevent VPC peering**

## Troubleshooting & Common Errors
- **No internet access:** Check IGW attachment and route tables
- **Cannot SSH to EC2:** Check security group and subnet
- **VPC peering not working:** Check for overlapping CIDR blocks
- **Resources can't talk:** Check NACLs and security groups

## Useful Links
- [VPC User Guide](https://docs.aws.amazon.com/vpc/latest/userguide/)
- [VPC Limits](https://docs.aws.amazon.com/vpc/latest/userguide/amazon-vpc-limits.html)

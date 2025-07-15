# EC2 Cheatsheet (Beginner-Friendly)

## Launching an EC2 Instance (Console)
1. Go to the EC2 Dashboard in AWS Console.
2. Click "Launch Instance".
3. Choose an AMI (e.g., Amazon Linux 2, Ubuntu, Windows).
4. Select an Instance Type (e.g., t3.micro for free tier).
5. Configure instance details (network, IAM role, monitoring).
6. Add storage (EBS volume size/type).
7. Add tags (e.g., Name=WebServer1).
8. Configure Security Group (open ports: 22 for SSH, 80 for HTTP).
9. Review and launch. Download the key pair for SSH access.

## Common CLI Commands
- **List Instances:** `aws ec2 describe-instances`
- **Launch Instance:** `aws ec2 run-instances --image-id ami-xxxx --instance-type t3.micro --key-name my-key --security-group-ids sg-xxxx --subnet-id subnet-xxxx`
- **Stop Instance:** `aws ec2 stop-instances --instance-ids i-xxxx`
- **Start Instance:** `aws ec2 start-instances --instance-ids i-xxxx`
- **Terminate Instance:** `aws ec2 terminate-instances --instance-ids i-xxxx`
- **Create AMI:** `aws ec2 create-image --instance-id i-xxxx --name "MyAMI"`
- **Attach EBS Volume:** `aws ec2 attach-volume --volume-id vol-xxxx --instance-id i-xxxx --device /dev/xvdf`

## Important Limits & Defaults
- **On-Demand Instances:** 20 per region (default, can request increase)
- **Elastic IPs:** 5 per region
- **Security Groups:** 250 per VPC
- **Key Pairs:** 5,000 per region
- **EBS Volumes:** 5,000 per region
- **Max EBS Volume Size:** 16 TiB
- **Max Instance Store Size:** Varies by instance type

## When to Use EC2
- You need full control over the OS and software stack
- You need to run legacy or custom applications
- You need persistent compute resources
- You need to attach GPUs or specialized hardware

## When NOT to Use EC2
- For simple static websites (use S3 + CloudFront)
- For event-driven or short-lived tasks (use Lambda)
- For managed databases (use RDS, DynamoDB)

## Exam Tips
- **Security Groups are stateful, NACLs are stateless**
- **EBS persists after instance stop/terminate (unless delete on termination is set)**
- **Spot Instances can be interrupted by AWS**
- **IAM roles are the secure way to grant permissions to EC2**
- **Elastic IPs are static, but incur cost if not attached**

## Troubleshooting & Common Errors
- **Cannot SSH:** Check security group (port 22), key pair, and public IP
- **Instance won’t start:** Check EBS volume state, instance limits, or AZ capacity
- **Lost data:** Instance Store is ephemeral; use EBS for persistence
- **Public IP changed:** Use Elastic IP to keep a static address
- **Permission denied:** Use IAM roles, not hardcoded credentials

## Useful Links
- [EC2 User Guide](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/)
- [EC2 Instance Types](https://aws.amazon.com/ec2/instance-types/)
- [EC2 Pricing](https://aws.amazon.com/ec2/pricing/)

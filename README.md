# Step-by-Step: Attaching a New EBS Volume to EC2
This guide provides detailed, step-by-step instructions for attaching and mounting a new Amazon EBS volume to a running EC2 instance using the AWS Console.

## Prerequisites  
  
- An AWS account with access to EC2 and EBS  
- A running EC2 instance  
- Appropriate IAM permissions  
  
## Steps  
  
### 1. Launch an EC2 Instance (if not already running)  
  
1. Go to the [AWS EC2 Console](https://console.aws.amazon.com/ec2/).  
2. Click **Instances** > **Launch Instances**.  
3. Select an AMI, instance type, and configure as needed.  
4. Add storage (default root volume is fine).  
5. Configure security group and key pair.  
6. Launch the instance and wait until it is running.

### 2. Identify the Instance’s Availability Zone  
  
1. In the EC2 Console, select your instance.  
2. Note the **Availability Zone** (e.g., `us-east-1a`) in the details.

### 3. Create a New EBS Volume  
  
1. In the sidebar, click **Elastic Block Store > Volumes**.  
2. Click **Create Volume**.  
3. Set the size, type, and **Availability Zone** (must match your instance).  
4. Click **Create Volume**.  
  
### 4. Attach the EBS Volume to the Instance  
  
1. Select the new volume in the Volumes list.  
2. Click **Actions > Attach Volume**.  
3. Select your instance and specify a device name (e.g., `/dev/xvdf`).  
4. Click **Attach**.  
  
### 5. Connect to Your EC2 Instance  
  
```bash  
ssh -i /path/to/your-key.pem ec2-user@<instance-public-ip>
```

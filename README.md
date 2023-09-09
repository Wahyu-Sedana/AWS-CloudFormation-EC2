# CloudFormation EC2 Instance Template

This repository contains an AWS CloudFormation template to create an EC2 instance with a corresponding security group that allows inbound traffic for HTTP, HTTPS, SSH, and RDS (MySQL Aurora).

## Prerequisites

Before you begin, make sure you have the following prerequisites:

- An AWS account.
- AWS CLI installed and configured with your account credentials.
- Basic knowledge of AWS CloudFormation.

## Usage

Follow these steps to deploy the EC2 instance using the CloudFormation template:

1. **Clone this repository**:

   ```bash
   git clone https://github.com/Wahyu-Sedana/AWS-CloudFormation-EC2.git
2. **Change directory**;
   
   ```bash
   cd cloudformation-ec2-template
  
3. **Deploy the CloudFormation stack**;

   ```bash
   aws cloudformation create-stack --stack-name your-stack-name --template-body file://cloudformation-ec2-template.yaml --capabilities CAPABILITY_NAMED_IAM

4. **Monitor the stack creation**;

   ```bash
   aws cloudformation wait stack-create-complete --stack-name your-stack-name

5. **Access your EC2 instance**;

   ```bash
   ssh -i YourKeyPair.pem ec2-user@public-ip

6. **Cleanup**;

   ```bash
   aws cloudformation delete-stack --stack-name your-stack-name

## Customization

You can customize the CloudFormation template by modifying the ec2-template.yaml file to meet your specific requirements. Make sure to review and adjust the security group rules and instance properties as needed.

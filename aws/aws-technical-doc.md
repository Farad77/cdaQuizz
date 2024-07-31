# AWS (Amazon Web Services) Technical Documentation

## Introduction

Amazon Web Services (AWS) is a comprehensive and widely adopted cloud platform, offering over 200 fully featured services from data centers globally. It provides a wide array of services including computing power, database storage, content delivery, and other functionality to help businesses scale and grow.

## Key Services

### Compute
1. EC2 (Elastic Compute Cloud): Virtual servers in the cloud
2. Lambda: Run code without provisioning or managing servers

### Storage
1. S3 (Simple Storage Service): Scalable object storage
2. EBS (Elastic Block Store): Persistent block storage for EC2

### Database
1. RDS (Relational Database Service): Managed relational databases
2. DynamoDB: Managed NoSQL database

### Networking
1. VPC (Virtual Private Cloud): Isolated cloud resources
2. Route 53: Scalable Domain Name System (DNS)

### Security
1. IAM (Identity and Access Management): Manage access to AWS services
2. WAF (Web Application Firewall): Protect web applications from common exploits

## Fundamental Concepts

### Regions and Availability Zones
- Regions are separate geographic areas
- Each region has multiple, isolated locations known as Availability Zones

### EC2 Instance Types
- General Purpose
- Compute Optimized
- Memory Optimized
- Storage Optimized
- Accelerated Computing

### S3 Storage Classes
- Standard
- Intelligent-Tiering
- Standard-Infrequent Access
- One Zone-Infrequent Access
- Glacier
- Glacier Deep Archive

### AWS Well-Architected Framework
1. Operational Excellence
2. Security
3. Reliability
4. Performance Efficiency
5. Cost Optimization
6. Sustainability

## Basic Operations

### Launching an EC2 Instance
1. Choose an Amazon Machine Image (AMI)
2. Select an instance type
3. Configure instance details
4. Add storage
5. Add tags
6. Configure security group
7. Review and launch

### Creating an S3 Bucket
1. Sign in to the AWS Management Console
2. Open the S3 console
3. Choose "Create bucket"
4. Enter a bucket name and region
5. Set properties and permissions
6. Review and create

## AWS CLI (Command Line Interface)

Basic structure of AWS CLI commands:
```
aws <service> <command> <arguments>
```

Example (list S3 buckets):
```
aws s3 ls
```

## IAM Best Practices
1. Lock away your AWS account root user access keys
2. Create individual IAM users
3. Use groups to assign permissions to IAM users
4. Grant least privilege
5. Enable MFA for privileged users
6. Use roles for applications that run on AWS EC2 instances

## Pricing Models
1. On-Demand
2. Reserved Instances
3. Spot Instances
4. Savings Plans

## AWS Free Tier
AWS offers a free tier that includes a number of services with a free usage tier for 12 months following your AWS sign-up date.


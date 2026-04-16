# AWS WordPress Infrastructure — Configuration Steps

## Overview
Manual deployment of WordPress on AWS using core infrastructure services.
No managed services (Elastic Beanstalk) were used — all configuration done manually
to demonstrate deep understanding of AWS fundamentals.

---

## Step 1 — VPC Setup
- Created a custom VPC with a defined CIDR block
- Configured public and private subnets across availability zones
- Set up Internet Gateway and attached it to the VPC
- Configured route tables for public subnet to allow internet traffic
- Kept private subnet isolated from direct internet access

## Step 2 — Security Groups
- Created Security Group for EC2: allowed inbound HTTP (80), HTTPS (443), SSH (22)
- Created Security Group for RDS: allowed inbound MySQL (3306) from EC2 Security Group only
- Created Security Group for EFS: allowed NFS (2049) from EC2 Security Group only
- Applied least-privilege principle — no unnecessary ports open

## Step 3 — RDS (MySQL Database)
- Launched RDS MySQL instance in the private subnet
- Configured Multi-AZ for high availability
- Set up automated backups and maintenance windows
- Created WordPress database and user credentials
- Confirmed EC2 could connect to RDS via Security Group rules

## Step 4 — EFS (Elastic File System)
- Created EFS file system for shared WordPress media storage
- Configured mount targets in each subnet
- Applied Security Group restricting access to EC2 only
- Mounted EFS on EC2 instance at /var/www/html/wp-content/uploads

## Step 5 — EC2 (Web Server)
- Launched EC2 instance (Amazon Linux 2) in the public subnet
- Installed Apache, PHP, and WordPress dependencies via SSH
- Mounted EFS to the WordPress uploads directory
- Configured WordPress wp-config.php with RDS database credentials
- Verified WordPress connected successfully to RDS database

## Step 6 — WordPress Configuration
- Completed WordPress installation through the web interface
- Configured permalinks, admin credentials, and site settings
- Tested media uploads to confirm EFS mounting was working correctly
- Verified full stack functionality end-to-end

---

## Key Technical Decisions

| Decision | Reason |
|---|---|
| Manual config over Elastic Beanstalk | Demonstrates deeper AWS knowledge |
| Private subnet for RDS | Security best practice — database not internet-facing |
| EFS for media storage | Allows shared storage across multiple EC2 instances if scaled |
| Security Groups per tier | Least-privilege access between each infrastructure layer |

---

## Skills Demonstrated
AWS VPC | EC2 | RDS | EFS | Security Groups | IAM | Linux | MySQL | WordPress | Networking

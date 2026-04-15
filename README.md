# AWS WordPress Infrastructure Project

## Overview
Production-grade WordPress deployment on AWS, built with core infrastructure 
services using fully manual configuration — no managed services like 
Elastic Beanstalk.

## Architecture
- **VPC** — Custom Virtual Private Cloud with public and private subnets
- **EC2** — Web server hosting the WordPress application
- **RDS** — Managed MySQL database for WordPress backend
- **EFS** — Elastic File System for shared WordPress media storage

## Key Technical Decisions
- Manual configuration chosen over Elastic Beanstalk to demonstrate 
  deeper understanding of AWS core services
- Multi-tier architecture separating web, application, and database layers
- Security groups configured to restrict access between tiers

## Skills Demonstrated
AWS | VPC | EC2 | RDS | EFS | Cloud Architecture | 
Infrastructure Security | Linux | MySQL

## Author
Troy Aremu-Ajagun | AWS Certified Solutions Architect
Ottawa, Canada
[LinkedIn](https://www.linkedin.com/in/troy-it/)

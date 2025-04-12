# AWS 2-Tier Infrastructure Project

This project demonstrates how to set up a scalable and secure 2-tier architecture on AWS using:

- VPC with public and private subnets
- NAT Gateways for outbound internet from private subnets
- Bastion host for SSH access to private EC2 instances
- Auto Scaling Group with Ubuntu-based instances
- Application Load Balancer routing traffic on port 8000

## 📦 Architecture Overview

- Public Subnet:
  - Bastion Host
  - Application Load Balancer
  - NAT Gateway
- Private Subnet:
  - EC2 Instances (launched via Auto Scaling Group)

## 🛠️ Tools Used

- AWS Console
- EC2, VPC, ASG, ALB, NAT Gateway
- Ubuntu AMI, Python3 HTTP Server
- SSH & SCP for remote access

## 🚀 Deployment Steps

Documented in detail in the attached [`AWS 2-Tier Project.docx`](./AWS%202-Tier%20Project.docx).

## 🔐 Security Config

- Bastion Host: SSH from anywhere
- Private EC2s: Accessible only via Bastion + ALB (HTTP 8000)
- Load Balancer: Public-facing on port 8000

## 🧹 Cleanup Instructions

1. Delete Load Balancer and Target Group
2. Delete ASG and Launch Template
3. Terminate all EC2 Instances
4. Delete NAT Gateways and VPC
5. Release Elastic IPs

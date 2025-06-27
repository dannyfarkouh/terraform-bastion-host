# Bastion Host Infrastructure on AWS (Terraform)

This project provisions secure AWS infrastructure using Terraform, demonstrating how to access a private EC2 instance via a Bastion Host. It follows common cloud architecture patterns for isolating resources while maintaining controlled administrative access.

## Overview

This Terraform configuration sets up:

- A custom **VPC** with:
  - One **public subnet** (for the Bastion Host)
  - One **private subnet** (for the internal EC2 instance)
- An **Internet Gateway** and route table for public subnet internet access
- A **Bastion Host EC2 instance** with a public IP
- A **Private EC2 instance** with no internet exposure
- **Security groups** configured to:
  - Allow SSH (port 22) to the Bastion Host from any IP (for demo purposes)
  - Allow SSH to the private EC2 instance *only* from the Bastion Host

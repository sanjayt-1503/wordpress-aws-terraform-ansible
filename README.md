# WordPress Deployment on AWS using Terraform & Ansible

![AWS](https://img.shields.io/badge/AWS-EC2-orange)
![Terraform](https://img.shields.io/badge/Terraform-1.9-purple)
![Ansible](https://img.shields.io/badge/Ansible-2.17-red)
![WordPress](https://img.shields.io/badge/WordPress-Latest-blue)

## Project Overview
This project automates the deployment of a production-ready WordPress application 
on AWS using Infrastructure as Code (IaC) principles. Terraform provisions the 
AWS infrastructure while Ansible handles server configuration and WordPress 
installation — making the entire setup automated, repeatable, and consistent.

## Architecture# wordpress-aws-terraform-ansible
Terraform → AWS EC2 + Security Groups → Ansible → Apache + MySQL + PHP + WordPress
## Tools & Technologies
| Category | Tools |
|---|---|
| Infrastructure as Code | Terraform 1.9 |
| Configuration Management | Ansible 2.17 |
| Cloud Provider | AWS (EC2, IAM, VPC, Security Groups) |
| Web Server | Apache |
| Database | MySQL |
| Application | WordPress |
| OS | Ubuntu 22.04 LTS |

## Project Structure
wordpress-aws-terraform-ansible/
├── main.tf
├── variables.tf
├── outputs.tf
├── playbook.yml
└── README.md
## 🔄 Workflow
1. Terraform provisions AWS EC2 instance with security groups
2. EC2 public IP is automatically saved to inventory file
3. Ansible connects to EC2 and installs Apache, MySQL, PHP
4. WordPress is downloaded, extracted, and configured
5. Application is live and accessible via public IP

## Prerequisites
- AWS CLI configured with access keys
- Terraform 1.9+ installed
- Ansible 2.17+ installed
- AWS Key Pair created

## How to Run

### Step 1 — Provision Infrastructure with Terraform
```bash
git clone https://github.com/your-username/wordpress-aws-terraform-ansible.git
cd wordpress-aws-terraform-ansible
terraform init
terraform plan
terraform apply
```

### Step 2 — Configure Server with Ansible
```bash
ansible-playbook -i inventory.ini playbook.yml --private-key your-key.pem -u ubuntu
```

### Step 3 — Access WordPress
http://your-ec2-public-ip/wordpress

## Security
- IAM roles with least privilege access
- Security groups configured for HTTP, HTTPS, and SSH only
- AWS VPC for network isolation

## Author
**Sanjay T**
- LinkedIn: https://www.linkedin.com/in/sanjay-t-38a5b4331/
- Email: sanjayt06.off@gmail.com

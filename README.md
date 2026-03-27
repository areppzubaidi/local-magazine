
# 📰 Local Magazine - Complete DevOps Project

![DevOps](https://img.shields.io/badge/DevOps-Complete-brightgreen)
![AWS](https://img.shields.io/badge/AWS-Free%20Tier-orange)
![Terraform](https://img.shields.io/badge/Terraform-IaC-purple)
![Ansible](https://img.shields.io/badge/Ansible-Automation-red)
![Docker](https://img.shields.io/badge/Docker-Container-blue)
![Ubuntu](https://img.shields.io/badge/Ubuntu-22.04-E95420)
![Nginx](https://img.shields.io/badge/Nginx-Alpine-009639)

A production-ready DevOps project demonstrating the complete deployment pipeline for a static magazine website using modern DevOps practices and tools.

## 📋 Table of Contents
- [Project Overview](#-project-overview)
- [Architecture](#-architecture)
- [Features](#-features)
- [Technologies Used](#-technologies-used)
- [Project Structure](#-project-structure)
- [Prerequisites](#-prerequisites)
- [Quick Deployment Guide](#-quick-deployment-guide)
- [Website Features](#-website-features)
- [AWS Resources](#-aws-resources-free-tier)
- [Troubleshooting](#-troubleshooting)
- [Clean Up](#-clean-up-resources)
- [Future Enhancements](#-future-enhancements)
- [License](#-license)

## 🎯 Project Overview

This project showcases a complete end-to-end DevOps workflow:

- **Develop** a static magazine-style website locally using HTML/CSS
- **Containerize** the application with Docker and Nginx Alpine
- **Version Control** the entire project with Git and GitHub
- **Provision** AWS infrastructure using Terraform (IaC)
- **Configure** and deploy using Ansible (Configuration Management)
- **Serve** the website from a Docker container running on EC2

The website is a modern, responsive magazine with homepage, articles, and about pages, featuring gradient backgrounds and emoji-based image placeholders.

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────────────────┐
│                         LOCAL DEVELOPMENT                           │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐             │
│  │   HTML/CSS   │  │   Docker     │  │   Ansible    │             │
│  │   Website    │  │   Container  │  │   Playbook   │             │
│  │   (Frontend) │  │   (Nginx)    │  │   (Config)   │             │
│  └──────────────┘  └──────────────┘  └──────────────┘             │
└─────────────────────────────────────────────────────────────────────┘
                                    │
                                    ▼
┌─────────────────────────────────────────────────────────────────────┐
│                    VERSION CONTROL (GitHub)                         │
│              https://github.com/areppzubaidi/local-magazine         │
└─────────────────────────────────────────────────────────────────────┘
                                    │
                                    ▼
┌─────────────────────────────────────────────────────────────────────┐
│                     AWS CLOUD (ap-southeast-1)                      │
│  ┌───────────────────────────────────────────────────────────────┐  │
│  │              TERRAFORM (Infrastructure as Code)               │  │
│  │  ┌─────────────────┐  ┌─────────────────────────────────────┐ │  │
│  │  │  EC2 Instance   │  │      Security Group                │ │  │
│  │  │  • t2.micro     │  │  • Port 22 (SSH) - Your IP        │ │  │
│  │  │  • Ubuntu 22.04 │  │  • Port 80 (HTTP) - 0.0.0.0/0     │ │  │
│  │  │  • 8GB Storage  │  │  • Port 443 (HTTPS) - Future      │ │  │
│  │  └─────────────────┘  └─────────────────────────────────────┘ │  │
│  └───────────────────────────────────────────────────────────────┘  │
│                            │                                        │
│                            ▼                                        │
│  ┌───────────────────────────────────────────────────────────────┐  │
│  │           ANSIBLE (Configuration Management)                  │  │
│  │  ✓ Update apt cache and install dependencies                  │  │
│  │  ✓ Install Docker CE and Docker Python module                │  │
│  │  ✓ Create website directory (/var/www/local-magazine)        │  │
│  │  ✓ Copy website files from local to EC2                      │  │
│  │  ✓ Deploy Nginx container with volume mount                  │  │
│  │  ✓ Configure container auto-restart                          │  │
│  └───────────────────────────────────────────────────────────────┘  │
│                            │                                        │
│                            ▼                                        │
│  ┌───────────────────────────────────────────────────────────────┐  │
│  │         DOCKER CONTAINER (nginx:alpine)                       │  │
│  │  ┌─────────────────────────────────────────────────────────┐  │  │
│  │  │           Static Website Files                          │  │  │
│  │  │  • index.html     - Homepage with featured articles    │  │  │
│  │  │  • article.html   - Full article content               │  │  │
│  │  │  • about.html     - About page with team info          │  │  │
│  │  │  • css/style.css  - Responsive styling with gradients  │  │  │
│  │  │  • images/        - SVG and emoji placeholders         │  │  │
│  │  └─────────────────────────────────────────────────────────┘  │  │
│  └───────────────────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────────────┘
                                    │
                                    ▼
                          🌐 Website Live at:
                      http://ec2-public-ip-address
```
## 📸 Screenshots

### Homepage

<img width="1204" height="867" alt="Screenshot 2026-03-27 at 8 29 25 PM" src="https://github.com/user-attachments/assets/d273cc6d-7bcc-4954-aaf3-cc1e6f7cfe81" />


*The main landing page featuring hero section and article cards*



### Deployment Process
<img width="615" height="871" alt="Screenshot 2026-03-27 at 8 31 11 PM" src="https://github.com/user-attachments/assets/f92c9fbb-519a-4ceb-8e4f-dafdc83e131c" />

*Terraform provisioning AWS infrastructure*

<img width="1414" height="524" alt="Screenshot 2026-03-27 at 8 31 31 PM" src="https://github.com/user-attachments/assets/dab2e441-c379-488b-a2a4-a075f1b8358d" />

*Ansible automating server configuration*


## ✨ Features

### DevOps Features
- ✅ **Infrastructure as Code**: Complete AWS infrastructure defined in Terraform
- ✅ **Configuration Management**: Automated server configuration with Ansible
- ✅ **Containerization**: Dockerized application for consistency
- ✅ **Version Control**: Full Git history on GitHub
- ✅ **Idempotent Deployments**: Safe to run playbooks multiple times
- ✅ **Cost Optimized**: AWS Free Tier compliant (t2.micro, 8GB root volume)
- ✅ **Secure by Design**: SSH key authentication, security groups

### Website Features
- ✅ **Modern Design**: Clean, magazine-style layout with CSS gradients
- ✅ **Fully Responsive**: Works on desktop, tablet, and mobile devices
- ✅ **3 Pages**: Homepage, Articles, About
- ✅ **Visual Elements**: Gradient backgrounds with emoji placeholders
- ✅ **Article Cards**: Featured articles with "Read More" links
- ✅ **Sticky Navigation**: Easy site navigation from any page
- ✅ **Hover Effects**: Interactive elements with smooth transitions
- ✅ **Footer**: Copyright information

## 🛠️ Technologies Used

| Category | Technology | Version | Purpose |
|----------|------------|---------|---------|
| **Frontend** | HTML5 | - | Semantic website structure |
| | CSS3 | - | Styling and responsive design |
| **Container** | Docker | 24.0+ | Containerization platform |
| | Nginx | Alpine | Web server |
| **Infrastructure** | Terraform | 1.5+ | AWS resource provisioning |
| | AWS EC2 | t2.micro | Compute instance |
| **Configuration** | Ansible | 8.0+ | Server automation |
| | Ubuntu | 22.04 LTS | Operating system |
| **Version Control** | Git | 2.40+ | Source code management |
| | GitHub | - | Repository hosting |

## 📁 Project Structure

```
local-magazine/
├── frontend/                      # Static website files
│   ├── index.html                 # Homepage with featured articles
│   ├── article.html               # Full articles page
│   ├── about.html                 # About page with team info
│   ├── css/
│   │   └── style.css              # Responsive CSS with gradients
│   └── images/                    # Image placeholders
│       ├── cafe.svg               # Coffee cup placeholder
│       ├── garden.svg             # Garden placeholder
│       └── festival.svg           # Festival placeholder
│
├── docker/
│   └── Dockerfile                 # Nginx Alpine container config
│
├── ansible/
│   ├── inventory.ini              # EC2 hosts (update with IP)
│   └── playbook.yml               # Deployment automation
│
├── terraform/
│   ├── main.tf                    # AWS resource definitions
│   ├── variables.tf               # Input variables
│   └── outputs.tf                 # Output values
│
├── .gitignore                     # Git ignore rules
└── README.md                      # This file
```

## 📋 Prerequisites

Before you begin, ensure you have the following installed and configured:

### Required Software
```bash
# Check installations
aws --version      # AWS CLI (v2.0+)
terraform --version # Terraform (v1.0+)
ansible --version   # Ansible (v8.0+)
docker --version    # Docker (v24.0+)
git --version       # Git (v2.40+)
```

### AWS Account Setup
1. Create an AWS account (Free Tier eligible)
2. Create an IAM user with programmatic access
3. Get Access Key ID and Secret Access Key
4. Configure AWS CLI:
```bash
aws configure
# Enter:
# AWS Access Key ID: YOUR_ACCESS_KEY
# AWS Secret Access Key: YOUR_SECRET_KEY
# Default region: ap-southeast-1
# Default output format: json
```

## 🚀 Quick Deployment Guide

### Step 1: Clone the Repository
```bash
git clone https://github.com/areppzubaidi/local-magazine.git
cd local-magazine
```

### Step 2: Create SSH Key Pair
```bash
# Create key pair in AWS
aws ec2 create-key-pair \
  --key-name magazine-key \
  --region ap-southeast-1 \
  --query 'KeyMaterial' \
  --output text > ~/.ssh/magazine-key.pem

# Set correct permissions
chmod 400 ~/.ssh/magazine-key.pem

# Verify key exists
ls -la ~/.ssh/magazine-key.pem
```

### Step 3: Deploy Infrastructure with Terraform
```bash
cd terraform

# Initialize Terraform
terraform init

# Review infrastructure changes
terraform plan -var="key_name=magazine-key"

# Deploy AWS resources
terraform apply -var="key_name=magazine-key" -auto-approve

# Wait for EC2 to initialize (30-60 seconds)
sleep 30

# Get EC2 public IP
EC2_IP=$(terraform output -raw instance_public_ip)
echo "EC2 Instance IP: $EC2_IP"
```

### Step 4: Configure Ansible Inventory
```bash
cd ../ansible

# Create inventory file with your EC2 IP
cat > inventory.ini << EOF
[web]
${EC2_IP} ansible_user=ubuntu ansible_ssh_private_key_file=~/.ssh/magazine-key.pem ansible_ssh_common_args='-o StrictHostKeyChecking=no'
EOF

# Verify inventory
cat inventory.ini
```

### Step 5: Test Ansible Connection
```bash
# Test SSH connection
ansible -i inventory.ini all -m ping

# Expected output:
# 54.xxx.xxx.xxx | SUCCESS => {
#     "changed": false,
#     "ping": "pong"
# }
```

### Step 6: Deploy Website with Ansible
```bash
# Run the deployment playbook
ansible-playbook -i inventory.ini playbook.yml

# This will:
# 1. Update apt cache
# 2. Install Docker CE
# 3. Create website directory
# 4. Copy website files
# 5. Deploy Nginx container
```

### Step 7: Verify Deployment
```bash
# Test the website with curl
curl http://${EC2_IP}

# Check Docker container status
ssh -i ~/.ssh/magazine-key.pem ubuntu@${EC2_IP} "sudo docker ps"

# View container logs
ssh -i ~/.ssh/magazine-key.pem ubuntu@${EC2_IP} "sudo docker logs local-magazine"

# Open in browser (macOS)
open http://${EC2_IP}

# For Linux
# xdg-open http://${EC2_IP}

# For Windows
# start http://${EC2_IP}
```

## 🎨 Website Features

### Pages Overview

#### Homepage (`index.html`)
- Hero section with gradient background
- Featured articles grid with 3 cards
- Article images with emoji placeholders
- "Read More" links to articles page

#### Articles Page (`article.html`)
- Full articles with metadata (author, date)
- Article images with gradient backgrounds
- Detailed content about local cafes and gardens
- Clean, readable typography

#### About Page (`about.html`)
- Mission statement
- Team information
- Contact details
- Company background

### Design Elements
- **Color Scheme**: Purple gradients (#667eea to #764ba2)
- **Typography**: System fonts (SF Pro, Roboto, etc.)
- **Responsive Breakpoints**: Mobile-first design at 768px
- **Interactive Elements**: Hover effects on cards and buttons
- **Sticky Navigation**: Header stays visible while scrolling

## 📊 AWS Resources (Free Tier)

| Resource | Specification | Free Tier Limit | Cost |
|----------|--------------|-----------------|------|
| **EC2 Instance** | t2.micro | 750 hours/month | Free |
| **Storage** | 8GB gp2 | 30GB free | Free |
| **Data Transfer** | In/Out | 15GB/month | Free |
| **Security Group** | 2 rules | Unlimited | Free |
| **Total Monthly Cost** | - | - | **$0.00** |

### Resource Details
- **Region**: ap-southeast-1 (Singapore)
- **AMI**: Ubuntu 22.04 LTS
- **Instance Type**: t2.micro (1 vCPU, 1GB RAM)
- **Root Volume**: 8GB General Purpose SSD (gp2)
- **Security Groups**: Port 22 (SSH), Port 80 (HTTP)

## 🔧 Troubleshooting

### SSH Connection Failed
```bash
# Check key permissions
chmod 400 ~/.ssh/magazine-key.pem

# Verify key exists
ls -la ~/.ssh/magazine-key.pem

# Test SSH manually
ssh -i ~/.ssh/magazine-key.pem ubuntu@${EC2_IP}

# Check instance state
aws ec2 describe-instances \
  --region ap-southeast-1 \
  --instance-ids $(cd terraform && terraform output -raw instance_id) \
  --query "Reservations[0].Instances[0].State.Name" \
  --output text
```

### Website Not Accessible (HTTP 404/503)
```bash
# Check if Docker container is running
ssh -i ~/.ssh/magazine-key.pem ubuntu@${EC2_IP} "sudo docker ps -a"

# If container is not running, start it
ssh -i ~/.ssh/magazine-key.pem ubuntu@${EC2_IP} "sudo docker start local-magazine"

# Check container logs
ssh -i ~/.ssh/magazine-key.pem ubuntu@${EC2_IP} "sudo docker logs local-magazine"

# Verify files are copied correctly
ssh -i ~/.ssh/magazine-key.pem ubuntu@${EC2_IP} "ls -la /var/www/local-magazine/"
```

### Ansible Connection Issues
```bash
# Test raw SSH first
ssh -i ~/.ssh/magazine-key.pem ubuntu@${EC2_IP}

# Check Python installation
ssh -i ~/.ssh/magazine-key.pem ubuntu@${EC2_IP} "python3 --version"

# Run Ansible with verbose output
ansible-playbook -i inventory.ini playbook.yml -vvv

# Check if ansible can ping
ansible -i inventory.ini all -m ping -v
```

### Security Group Issues
```bash
# Check security group rules
cd terraform
SG_ID=$(terraform output -raw security_group_id)
aws ec2 describe-security-groups \
  --group-ids ${SG_ID} \
  --region ap-southeast-1 \
  --query "SecurityGroups[0].IpPermissions"

# Verify ports are open
nc -zv ${EC2_IP} 22  # SSH
nc -zv ${EC2_IP} 80  # HTTP
```

### Common Error Messages

| Error | Solution |
|-------|----------|
| `Permission denied (publickey)` | Check key permissions: `chmod 400 ~/.ssh/magazine-key.pem` |
| `Connection timed out` | Verify EC2 is running and security group allows port 22 |
| `Host key verification failed` | Run: `ssh-keyscan -H ${EC2_IP} >> ~/.ssh/known_hosts` |
| `No module named docker` | Install Docker Python module: `pip install docker` |
| `Port 80 already in use` | Stop existing container: `docker stop local-magazine` |

## 🧹 Clean Up Resources

To avoid ongoing AWS charges, destroy all resources when not in use:

```bash
cd terraform

# Destroy all infrastructure
terraform destroy -var="key_name=magazine-key" -auto-approve

# Delete SSH key from AWS
aws ec2 delete-key-pair \
  --key-name magazine-key \
  --region ap-southeast-1

# Remove local SSH key (optional)
rm ~/.ssh/magazine-key.pem
```

## 📈 Future Enhancements

- [ ] **CI/CD Pipeline**: Add GitHub Actions for automated deployments
- [ ] **HTTPS**: Implement Let's Encrypt SSL certificate
- [ ] **CDN**: Add CloudFront for global content delivery
- [ ] **Custom Domain**: Route53 configuration with custom domain
- [ ] **Monitoring**: Prometheus and Grafana for metrics
- [ ] **Logging**: ELK stack (Elasticsearch, Logstash, Kibana)
- [ ] **Database**: Add PostgreSQL for dynamic content
- [ ] **Authentication**: User login and profiles
- [ ] **CMS**: Content Management System integration
- [ ] **Load Balancer**: Auto-scaling with Application Load Balancer
- [ ] **Backup**: Automated EBS snapshots
- [ ] **Alerts**: CloudWatch alarms for monitoring

## 📝 Best Practices Implemented

- ✅ **Infrastructure as Code**: All resources defined in Terraform
- ✅ **Immutable Infrastructure**: Containerized application
- ✅ **Idempotent Deployments**: Ansible playbooks safe to re-run
- ✅ **Security Groups**: Principle of least privilege
- ✅ **SSH Key Authentication**: No password-based SSH
- ✅ **Version Control**: Full Git history
- ✅ **Documentation**: Comprehensive README
- ✅ **Free Tier Optimized**: No cost beyond free tier
- ✅ **Modular Code**: Separated concerns (frontend, infra, config)

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is open source and available under the MIT License.

```
MIT License

Copyright (c) 2024 Arepp Zubaidi

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions...

Full license text available in the repository.
```

## 📧 Contact & Support

- **GitHub**: [@areppzubaidi](https://github.com/areppzubaidi)
- **Project URL**: [https://github.com/areppzubaidi/local-magazine](https://github.com/areppzubaidi/local-magazine)
- **Issues**: [Report a bug or request feature](https://github.com/areppzubaidi/local-magazine/issues)

## 🌟 Show Your Support

If this project helped you learn DevOps or saved you time, please give it a ⭐️ on GitHub!

---

## 🎯 Quick Commands Reference

```bash
# Complete deployment in one command
cd ~/local-magazine && \
./deploy.sh  # Create this script with the deployment steps

# Check deployment status
curl -I http://$(cd terraform && terraform output -raw instance_public_ip)

# SSH into EC2
ssh -i ~/.ssh/magazine-key.pem ubuntu@$(cd terraform && terraform output -raw instance_public_ip)

# View Docker logs
ssh -i ~/.ssh/magazine-key.pem ubuntu@$(cd terraform && terraform output -raw instance_public_ip) "sudo docker logs -f local-magazine"

# Restart container
ssh -i ~/.ssh/magazine-key.pem ubuntu@$(cd terraform && terraform output -raw instance_public_ip) "sudo docker restart local-magazine"

# Update website content
scp -i ~/.ssh/magazine-key.pem -r frontend/* ubuntu@$(cd terraform && terraform output -raw instance_public_ip):/tmp/ && \
ssh -i ~/.ssh/magazine-key.pem ubuntu@$(cd terraform && terraform output -raw instance_public_ip) "sudo cp -r /tmp/* /var/www/local-magazine/ && sudo docker restart local-magazine"
```

---

**Built with ☕ and DevOps best practices**

*Last Updated: March 2026*
```

Now copy this entire markdown code and paste it into your README.md file:

```bash
cd ~/local-magazine
cat > README.md << 'EOF'
[PASTE THE ENTIRE MARKDOWN ABOVE HERE]
EOF

# Then push to GitHub
git add README.md
git commit -m "Add comprehensive README with complete documentation"
git push origin main
```

This README includes:
- ✅ Professional badges and formatting
- ✅ Detailed architecture diagram
- ✅ Complete setup instructions
- ✅ Troubleshooting guide
- ✅ Quick commands reference
- ✅ Future enhancements
- ✅ License information
- ✅ Contact details

Your GitHub repository now has a professional, comprehensive README that will impress recruiters and help users deploy your project! 🚀
